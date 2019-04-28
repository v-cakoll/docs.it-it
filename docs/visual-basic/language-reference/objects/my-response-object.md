---
title: Oggetto My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 2f72f493d99c1e0b0469150c041649486e5ed124
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794992"
---
# <a name="myresponse-object"></a><span data-ttu-id="43176-102">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="43176-102">My.Response Object</span></span>
<span data-ttu-id="43176-103">Ottiene il <xref:System.Web.HttpResponse> oggetto associato di <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="43176-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="43176-104">Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.</span><span class="sxs-lookup"><span data-stu-id="43176-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43176-105">Note</span><span class="sxs-lookup"><span data-stu-id="43176-105">Remarks</span></span>  
 <span data-ttu-id="43176-106">Il `My.Response` oggetto contiene l'oggetto corrente <xref:System.Web.HttpResponse> oggetto associato alla pagina.</span><span class="sxs-lookup"><span data-stu-id="43176-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="43176-107">Il `My.Response` oggetto è disponibile solo per [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="43176-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43176-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="43176-108">Example</span></span>  
 <span data-ttu-id="43176-109">L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43176-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="43176-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43176-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="43176-111">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="43176-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
