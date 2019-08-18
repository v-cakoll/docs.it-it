---
title: Oggetto My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567448"
---
# <a name="myresponse-object"></a><span data-ttu-id="28ccc-102">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="28ccc-102">My.Response Object</span></span>
<span data-ttu-id="28ccc-103">Ottiene l' <xref:System.Web.HttpResponse> oggetto associato <xref:System.Web.UI.Page>all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="28ccc-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="28ccc-104">Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.</span><span class="sxs-lookup"><span data-stu-id="28ccc-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28ccc-105">Note</span><span class="sxs-lookup"><span data-stu-id="28ccc-105">Remarks</span></span>  
 <span data-ttu-id="28ccc-106">L' `My.Response` oggetto contiene l'oggetto <xref:System.Web.HttpResponse> corrente associato alla pagina.</span><span class="sxs-lookup"><span data-stu-id="28ccc-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="28ccc-107">L' `My.Response` oggetto è disponibile solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="28ccc-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ccc-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="28ccc-108">Example</span></span>  
 <span data-ttu-id="28ccc-109">Nell'esempio seguente viene ottenuta la raccolta di `My.Request` intestazioni dall'oggetto e `My.Response` viene utilizzato l'oggetto per scriverlo nella pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="28ccc-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="28ccc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28ccc-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="28ccc-111">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="28ccc-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
