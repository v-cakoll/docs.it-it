---
title: 'Procedura: Impostare il titolo di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940779"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Procedura: Impostare il titolo di una finestra da una pagina
Questo esempio illustra come impostare il titolo della finestra in cui è ospitato un <xref:System.Windows.Controls.Page> oggetto.  
  
## <a name="example"></a>Esempio  
 Una pagina può modificare il titolo della finestra che lo ospita impostando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come segue:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> L'impostazione <xref:System.Windows.Controls.Page.Title%2A> della proprietà di una pagina non comporta la modifica del valore del titolo della finestra. <xref:System.Windows.Controls.Page.Title%2A> Specifica invece il nome di una voce di pagina nella cronologia di navigazione.
