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
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818995"
---
# <a name="myresponse-object"></a>Oggetto My.Response
Ottiene il <xref:System.Web.HttpResponse> oggetto associato di <xref:System.Web.UI.Page>. Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.  
  
## <a name="remarks"></a>Note  
 Il `My.Response` oggetto contiene l'oggetto corrente <xref:System.Web.HttpResponse> oggetto associato alla pagina.  
  
 Il `My.Response` oggetto è disponibile solo per [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applicazioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.HttpResponse>
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
