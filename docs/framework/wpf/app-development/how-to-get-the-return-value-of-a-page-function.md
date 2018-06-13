---
title: 'Procedura: ottenere il valore restituito di una funzione di pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: 2994a0fd7a192716a829c8290f030788da74cec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545269"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="909ea-102">Procedura: ottenere il valore restituito di una funzione di pagina</span><span class="sxs-lookup"><span data-stu-id="909ea-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="909ea-103">Questo esempio illustra come ottenere il risultato restituito da una funzione di pagina.</span><span class="sxs-lookup"><span data-stu-id="909ea-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="909ea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="909ea-104">Example</span></span>  
 <span data-ttu-id="909ea-105">Per ottenere il risultato restituito da una funzione di pagina, è necessario gestire <xref:System.Windows.Navigation.PageFunction%601.Return> della funzione di pagina che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="909ea-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="909ea-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="909ea-106">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
