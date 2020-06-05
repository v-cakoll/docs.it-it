---
title: Oggetto My.Response
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 962108264563c5e0b2894c5c856a5f23a3c1a8b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372460"
---
# <a name="myresponse-object"></a>Oggetto My.Response
Ottiene l' <xref:System.Web.HttpResponse> oggetto associato all'oggetto <xref:System.Web.UI.Page> . Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.  
  
## <a name="remarks"></a>Commenti  
 L' `My.Response` oggetto contiene l' <xref:System.Web.HttpResponse> oggetto corrente associato alla pagina.  
  
 L' `My.Response` oggetto è disponibile solo per le applicazioni ASP.NET.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuta la raccolta di intestazioni dall' `My.Request` oggetto e viene utilizzato l' `My.Response` oggetto per scriverlo nella pagina ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.HttpResponse>
- [Oggetto My.Request](my-request-object.md)
