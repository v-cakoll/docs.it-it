---
title: 'Procedura: Impostare il titolo di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357508"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Procedura: Impostare il titolo di una finestra da una pagina
In questo esempio viene illustrato come impostare il titolo della finestra in cui un <xref:System.Windows.Controls.Page> è ospitato.  
  
## <a name="example"></a>Esempio  
 Una pagina è possibile modificare il titolo della finestra che la ospita impostando il <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come illustrato di seguito:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  L'impostazione di <xref:System.Windows.Controls.Page.Title%2A> non modifica il valore del titolo della finestra proprietà di una pagina. Al contrario, <xref:System.Windows.Controls.Page.Title%2A> specifica il nome di una voce di pagina nella cronologia di navigazione.
