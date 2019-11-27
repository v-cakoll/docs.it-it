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
# <a name="myresponse-object"></a>Oggetto My.Response
Ottiene l'oggetto <xref:System.Web.HttpResponse> associato al <xref:System.Web.UI.Page>. Questo oggetto consente di inviare dati di risposta HTTP a un client e contiene informazioni su tale risposta.  
  
## <a name="remarks"></a>Osservazioni  
 L'oggetto `My.Response` contiene l'oggetto <xref:System.Web.HttpResponse> corrente associato alla pagina.  
  
 L'oggetto `My.Response` è disponibile solo per le applicazioni ASP.NET.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuta la raccolta di intestazioni dall'oggetto `My.Request` e viene utilizzato l'oggetto `My.Response` per scriverlo nella pagina ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.HttpResponse>
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
