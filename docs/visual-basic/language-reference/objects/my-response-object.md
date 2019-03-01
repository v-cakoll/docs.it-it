---
title: Oggetto My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 5677108ac31733577915e15972386d8de5ccba49
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203350"
---
# <a name="myresponse-object"></a><span data-ttu-id="a8950-102">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="a8950-102">My.Response Object</span></span>
<span data-ttu-id="a8950-103">Ottiene il <xref:System.Web.HttpResponse> oggetto associato di <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="a8950-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="a8950-104">Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.</span><span class="sxs-lookup"><span data-stu-id="a8950-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8950-105">Note</span><span class="sxs-lookup"><span data-stu-id="a8950-105">Remarks</span></span>  
 <span data-ttu-id="a8950-106">Il `My.Response` oggetto contiene l'oggetto corrente <xref:System.Web.HttpResponse> oggetto associato alla pagina.</span><span class="sxs-lookup"><span data-stu-id="a8950-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="a8950-107">Il `My.Response` oggetto è disponibile solo per [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a8950-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8950-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8950-108">Example</span></span>  
 <span data-ttu-id="a8950-109">L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a8950-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a8950-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8950-110">See also</span></span>
- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="a8950-111">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="a8950-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
