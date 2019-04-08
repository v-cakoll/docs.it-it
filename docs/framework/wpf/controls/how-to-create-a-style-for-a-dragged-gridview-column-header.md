---
title: "Procedura: Creare uno stile per un'intestazione di colonna GridView trascinata"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090095"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Procedura: Creare uno stile per un'intestazione di colonna GridView trascinata
Questo esempio viene illustrato come modificare l'aspetto di una classe trascinata <xref:System.Windows.Controls.GridViewColumnHeader> quando l'utente modifica la posizione di una colonna.  
  
## <a name="example"></a>Esempio  
 Quando si trascina un'intestazione di colonna in un'altra posizione in una <xref:System.Windows.Controls.ListView> che usa <xref:System.Windows.Controls.GridView> per la modalità di visualizzazione, la colonna viene spostata nella nuova posizione. Mentre si trascina l'intestazione di colonna, oltre a nell'intestazione originale verrà visualizzata una copia a virgola mobile dell'intestazione. Un'intestazione di colonna in una <xref:System.Windows.Controls.GridView> rappresentato da un <xref:System.Windows.Controls.GridViewColumnHeader> oggetto.  
  
 Per personalizzare l'aspetto delle intestazioni originale e a virgola mobile, è possibile impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare il <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>. Questi <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> vengono applicati quando le <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà `true` e il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> valore della proprietà è <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Quando l'utente preme il pulsante del mouse e tiene premuto mentre il puntatore del mouse si sofferma sul <xref:System.Windows.Controls.GridViewColumnHeader>, il <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> cambia di valore della proprietà `true`. Analogamente, quando l'utente inizia l'operazione di trascinamento, il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> le modifiche alle proprietà <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.  
  
 Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare il <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.Background%2A> colori delle intestazioni originale e a virgola mobile quando l'utente trascina una colonna in una nuova posizione.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
