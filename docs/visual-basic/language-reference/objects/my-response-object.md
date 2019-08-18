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
# <a name="myresponse-object"></a>Oggetto My.Response
Ottiene l' <xref:System.Web.HttpResponse> oggetto associato <xref:System.Web.UI.Page>all'oggetto. Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.  
  
## <a name="remarks"></a>Note  
 L' `My.Response` oggetto contiene l'oggetto <xref:System.Web.HttpResponse> corrente associato alla pagina.  
  
 L' `My.Response` oggetto è disponibile solo per le applicazioni ASP.NET.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuta la raccolta di `My.Request` intestazioni dall'oggetto e `My.Response` viene utilizzato l'oggetto per scriverlo nella pagina ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.HttpResponse>
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
