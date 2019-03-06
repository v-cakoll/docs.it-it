---
title: "Procedura: Ottenere tutti i Windows in un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378824"
---
# <a name="how-to-get-all-windows-in-an-application"></a>Procedura: Ottenere tutti i Windows in un'applicazione
In questo esempio viene illustrato come ottenere tutti i <xref:System.Windows.Window> oggetti in un'applicazione.  
  
## <a name="example"></a>Esempio  
 Ogni creazione di un'istanza <xref:System.Windows.Window> dell'oggetto, se visibile o No, viene aggiunto automaticamente a una raccolta di riferimenti a finestra gestito da <xref:System.Windows.Application>ed esposto da <xref:System.Windows.Application.Windows%2A>.  
  
 È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le istanze di windows usando il codice seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
