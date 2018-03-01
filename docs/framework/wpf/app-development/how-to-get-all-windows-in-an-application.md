---
title: 'Procedura: ottenere tutte le finestre in un''applicazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fdb1baad8b779b6ef0443a05e5f6575b552b1c19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="06470-102">Procedura: ottenere tutte le finestre in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="06470-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="06470-103">In questo esempio viene illustrato come ottenere tutti <xref:System.Windows.Window> oggetti in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="06470-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06470-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="06470-104">Example</span></span>  
 <span data-ttu-id="06470-105">Ogni creazione di un'istanza <xref:System.Windows.Window> dell'oggetto, se visibile oppure No, viene automaticamente aggiunto a una raccolta di riferimenti di finestre che è gestito da <xref:System.Windows.Application>ed esposto da <xref:System.Windows.Application.Windows%2A>.</span><span class="sxs-lookup"><span data-stu-id="06470-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="06470-106">È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le istanze di windows utilizzando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="06470-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
