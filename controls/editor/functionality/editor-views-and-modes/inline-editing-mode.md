---
title: Inline Editing Mode
page_title: Inline Editing Mode | UI for ASP.NET AJAX Documentation
description: Inline Editing Mode
slug: editor/functionality/editor-views-and-modes/inline-editing-mode
tags: inline,editing,mode
published: True
position: 2
---

# Inline Editing Mode



This article showcases the __Inline Editing__ functionality of the	__Telerik ASP.NET AJAX Editor__ that is available as of	__Q3 2014__. You can seeit in action in the[Inline Editing](http://demos.telerik.com/aspnet-ajax/editor/examples/inlineediting/defaultcs.aspx)	live demo.

This article contains the following sections:

* [What is Inline Editing](#what-is-inline-editing)—the key features and specifics of the inline editing mode.

* [Enabling RadEditor Inline Editing](#enabling-radeditor-inline-editing)—the basic steps to start using the inline editing together with an example.

* [Customizing the Toolbar](#customizing-the-toolbar)—how to customize the editor toolbar by setting its dimensions and choosing tools.

## What is Inline Editing

Inline Editing feature enables you to directly edit the web page content by using __RadEditor__ and at the same time to have an overview of the real layout and appearance.

Here are the key features of the __Inline Editing__ mode:

* __Click__ on the content to __start editing__. At this point the editor toolbar appears above the content. It uses fade animation by default (see __Example 2__).

* The default toolbar contains only the most commonly used tools (__Figure 1__).

* While not editing, the borders, [modules]({%slug editor/functionality/modules/overview%}) and the default buttons for switching between the different [edit modes]({%slug editor/functionality/editor-views-and-modes/edit-modes%}) are hidden.

* You can switch to HTML edit mode via the __ToggleEditMode__ button (__Figure 1__).

* The height of the editor is based on the content height via its [AutoResizeHeight feature]({%slug editor/managing-content/automatic-height-resize%}) that is enabled by default and cannot be disabled.

* You can set the __Width__ property of the control so it matches your current design and layout.

* The [ContentAreaMode]({%slug editor/functionality/editor-views-and-modes/contentareamode-property%}) of the editor is set to __Div__. Thus, the content area becomes part of the current page and the existing style sheets are automatically inherited.

* You can execute custom client-side code when finished with the inline-editing (i.e., clicking outside of the editor's content area) by handling the [OnClientInlineEditCompleted]({%slug editor/client-side-programming/events/onclientinlineeditcompleted%}) event.
>caption Figure 1: RadEditor with Inline Editing enabled

![editor-inline-editing-overview](images/editor-inline-editing-overview.png)

## Enabling RadEditor Inline Editing

The inline editing functionality is controlled by the __EditType__ property of __RadEditor__. To enable it:

1. Set the __EditType__ property to __Inline__.

1. Wrap your already existing layout into the __Content__ tag of __RadEditor__ (see __Example 1__).

1. Optionally, set the __Width__ property of the editor so it fits your layout.

__Example 1__: Enabling RadEditor inline editing:

````ASPNET
			<telerik:RadEditor ID="RadEditor1" runat="server" EditType="Inline">
					<Content>
						<div style="width: 420px">
							<h2 class="titleText">RadEditor for ASP.NET AJAX</h2>
							<p style="text-align: justify;">
								<span style="color: #4f6128; font-size: 19px;"><strong>RadEditor</strong></span><span style="color: #4f6128;">
								</span>is not simply an HTML
								<a href="#HTMLDescription">
									<sup>1</sup>
								</a> Editor. It is what Microsoft chose to use in <strong>MSDN</strong>, <strong>CodePlex</strong>, <strong>TechNet</strong>, <strong>MCMS</strong> and even as an alternative to the default editor in
								<a href="http://www.telerik.com/products/aspnet-ajax/sharepoint.aspx">SharePoint</a>.
							</p>
						</div>
					</Content>
				</telerik:RadEditor>
````



The result of this example is displayed in __Figure 1__.

## Customizing the Toolbar

The toolbar width has a default value that accommodates the default toolbar. If you set the __Width__ property of the editor, however, the toolbar will also inherit this value. If you need to set different width only for the toolbar, you can use the __ToolsWidth__ property.

You can see how to add/remove tools in the toolbar in the following help articles:

* [Configure the toolbar using an XML ToolsFile]({%slug editor/functionality/toolbars/using-toolsfile.xml%})

* [Adding Standard Buttons]({%slug editor/functionality/toolbars/buttons/add-standard-buttons%})

* [Adding Your Own Buttons]({%slug editor/functionality/toolbars/buttons/add-your-own-buttons%})

By default, the toolbar shows with a fade-in animation when the editor is in inline edit mode. You can use the __AnimationSettings__inner tag of the control to disable the animation or to change its duration via the __Type__ and__Duration__ properties of the __ToolbarAnimations__ section:

__Example 2__: Changing the animation settings of RadEditor in Inline edit mode on the server

````ASPNET
			<telerik:RadEditor ID="RadEditor1" runat="server" EditType="Inline">
				<AnimationSettings>
					<ToolbarAnimation Type="Fade" Duration="1000" />
				</AnimationSettings>
			</telerik:RadEditor>
````



You can also change the animation on the client:

__Example 3__: Changing the animation settings of RadEditor in Inline edit mode on the client

````JavaScript
				function changeAnimationSettings() {
					var editor = $find("<%=RadEditor1.ClientID%>");
					var toolAdapter = editor.get_toolAdapter();
					toolAdapter.set_animationType(Telerik.Web.UI.Editor.EditorToolBarAnimationType.None); //or Telerik.Web.UI.Editor.EditorToolBarAnimationType.Fade which is the default value
					toolAdapter.set_animationDuration(500);
				}
````



# See Also

 * [ContentAreaMode Property]({%slug editor/functionality/editor-views-and-modes/contentareamode-property%})

 * [Edit Modes]({%slug editor/functionality/editor-views-and-modes/edit-modes%})

 * [Overview]({%slug editor/functionality/modules/overview%})

 * [Using ToolsFile.xml]({%slug editor/functionality/toolbars/using-toolsfile.xml%})

 * [Add Standard Buttons]({%slug editor/functionality/toolbars/buttons/add-standard-buttons%})

 * [Add Your Own Buttons]({%slug editor/functionality/toolbars/buttons/add-your-own-buttons%})

 * [Automatic Height Resize]({%slug editor/managing-content/automatic-height-resize%})

 * [OnClientInlineEditCompleted]({%slug editor/client-side-programming/events/onclientinlineeditcompleted%})

 * [Live demo: Editor - Inline Editing](http://demos.telerik.com/aspnet-ajax/editor/examples/inlineediting/defaultcs.aspx)