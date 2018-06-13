---
title: "Procedura: creare uno stile per un'intestazione di colonna GridView trascinata"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: 2e57b4cb1b8ddb90e8e6e0abc6db3e7f0b864cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554573"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Procedura: creare uno stile per un'intestazione di colonna GridView trascinata
In questo esempio viene illustrato come modificare l'aspetto di un elemento trascinato <xref:System.Windows.Controls.GridViewColumnHeader> quando l'utente modifica la posizione di una colonna.  
  
## <a name="example"></a>Esempio  
 Quando si trascina un'intestazione di colonna in un'altra posizione in un <xref:System.Windows.Controls.ListView> che utilizza <xref:System.Windows.Controls.GridView> per la modalità di visualizzazione, la colonna viene spostata nella nuova posizione. Mentre si trascina l'intestazione di colonna, verrà visualizzata una copia mobile dell'intestazione oltre l'intestazione originale. Un'intestazione di colonna in un <xref:System.Windows.Controls.GridView> è rappresentato da un <xref:System.Windows.Controls.GridViewColumnHeader> oggetto.  
  
 Per personalizzare l'aspetto di intestazioni originali e a virgola mobile, è possibile impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare il <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Questi <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> vengono applicate quando la <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà è `true` e <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> valore della proprietà è <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Quando l'utente preme il pulsante del mouse e tiene premuto mentre il mouse si sofferma sul <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia di valore della proprietà `true`. Analogamente, quando l'utente inizia l'operazione di trascinamento, il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> le modifiche alle proprietà <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare il <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.Background%2A> colori delle intestazioni originali e mobili quando l'utente trascina una colonna in una nuova posizione.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
