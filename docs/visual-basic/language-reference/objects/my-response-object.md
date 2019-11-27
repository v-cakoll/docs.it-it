---
title: Oggetto My.Response
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350649"
---
# <a name="myresponse-object"></a><span data-ttu-id="fd7dc-102">Oggetto My.Response</span><span class="sxs-lookup"><span data-stu-id="fd7dc-102">My.Response Object</span></span>
<span data-ttu-id="fd7dc-103">Ottiene l'oggetto <xref:System.Web.HttpResponse> associato al <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="fd7dc-104">Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd7dc-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fd7dc-105">Remarks</span></span>  
 <span data-ttu-id="fd7dc-106">L'oggetto `My.Response` contiene l'oggetto <xref:System.Web.HttpResponse> corrente associato alla pagina.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="fd7dc-107">L'oggetto `My.Response` è disponibile solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd7dc-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd7dc-108">Example</span></span>  
 <span data-ttu-id="fd7dc-109">Nell'esempio seguente viene ottenuta la raccolta di intestazioni dall'oggetto `My.Request` e viene utilizzato l'oggetto `My.Response` per scriverlo nella pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fd7dc-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd7dc-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="fd7dc-111">Oggetto My.Request</span><span class="sxs-lookup"><span data-stu-id="fd7dc-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
