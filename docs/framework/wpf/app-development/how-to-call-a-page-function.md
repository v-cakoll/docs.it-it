---
title: 'Procedura: Chiamare una funzione di pagina'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: e7c7c5ef98feeb4c5557295d92a8b219d9799865
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364147"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="ffbad-102">Procedura: Chiamare una funzione di pagina</span><span class="sxs-lookup"><span data-stu-id="ffbad-102">How to: Call a Page Function</span></span>
<span data-ttu-id="ffbad-103">Questo esempio illustra come chiamare una funzione di pagina da una [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="ffbad-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffbad-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffbad-104">Example</span></span>  
 <span data-ttu-id="ffbad-105">È possibile passare a una funzione di pagina usando [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]un, nello stesso modo in cui è possibile passare a una pagina.</span><span class="sxs-lookup"><span data-stu-id="ffbad-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="ffbad-106">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ffbad-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="ffbad-107">Se è necessario passare i dati alla funzione di pagina, è possibile crearne un'istanza e passare i dati impostando una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ffbad-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="ffbad-108">In alternativa, come illustrato nell'esempio seguente, è possibile passare i dati usando un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="ffbad-108">Or, as the following example shows, you can pass the data using a non-parameterless constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="ffbad-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffbad-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
