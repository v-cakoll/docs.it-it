---
title: Oggetto My. Request (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 08212dc5fe563ce84be02ab706b56195a0636894
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836623"
---
# <a name="myrequest-object"></a><span data-ttu-id="c270d-102">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="c270d-102">My.Request Object</span></span>
<span data-ttu-id="c270d-103">Ottiene l'oggetto <xref:System.Web.HttpRequest> per la pagina richiesta.</span><span class="sxs-lookup"><span data-stu-id="c270d-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c270d-104">Note</span><span class="sxs-lookup"><span data-stu-id="c270d-104">Remarks</span></span>  
 <span data-ttu-id="c270d-105">L'oggetto `My.Request` contiene informazioni sulla richiesta HTTP corrente.</span><span class="sxs-lookup"><span data-stu-id="c270d-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="c270d-106">L'oggetto `My.Request` è disponibile solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c270d-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c270d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c270d-107">Example</span></span>  
 <span data-ttu-id="c270d-108">L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c270d-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c270d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c270d-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="c270d-110">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="c270d-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
