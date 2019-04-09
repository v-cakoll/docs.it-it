---
title: 'Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209424"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a>Procedura: Posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox
In questo esempio mostra come posizionare un menu contestuale personalizzato per un <xref:System.Windows.Controls.RichTextBox>.  
  
 Quando si implementa un menu contestuale personalizzato per un oggetto **RichTextBox**, si è responsabili della gestione del posizionamento del menu contestuale.  Per impostazione predefinita, un menu contestuale personalizzato si apre al centro dell'oggetto **RichTextBox**.  
  
## <a name="example"></a>Esempio  
 Per eseguire l'override del comportamento del posizionamento predefinito, aggiungere un listener per il <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> evento.  L'esempio seguente illustra come eseguire questa operazione a livello di codice.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata un'implementazione corrispondente <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> listener di eventi.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
