---
title: Oggetto My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: d5f49529a2593093a234babc22f64b591ea3cc61
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929551"
---
# <a name="myresponse-object"></a><span data-ttu-id="9cb1b-102">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="9cb1b-102">My.Response Object</span></span>
<span data-ttu-id="9cb1b-103">Ottiene il <xref:System.Web.HttpResponse> oggetto associato di <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="9cb1b-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="9cb1b-104">Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.</span><span class="sxs-lookup"><span data-stu-id="9cb1b-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cb1b-105">Note</span><span class="sxs-lookup"><span data-stu-id="9cb1b-105">Remarks</span></span>  
 <span data-ttu-id="9cb1b-106">Il `My.Response` oggetto contiene l'oggetto corrente <xref:System.Web.HttpResponse> oggetto associato alla pagina.</span><span class="sxs-lookup"><span data-stu-id="9cb1b-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="9cb1b-107">Il `My.Response` oggetto è disponibile solo per [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9cb1b-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cb1b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9cb1b-108">Example</span></span>  
 <span data-ttu-id="9cb1b-109">L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9cb1b-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="9cb1b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cb1b-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="9cb1b-111">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="9cb1b-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
