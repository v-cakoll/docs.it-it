---
title: Oggetto My. Request (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 7a4e292968cf1d30977b8cacdc8f77152e5cc770
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200962"
---
# <a name="myrequest-object"></a>Oggetto My.Request
Ottiene l'oggetto <xref:System.Web.HttpRequest> per la pagina richiesta.  
  
## <a name="remarks"></a>Note  
 L'oggetto `My.Request` contiene informazioni sulla richiesta HTTP corrente.  
  
 L'oggetto `My.Request` è disponibile solo per le applicazioni ASP.NET.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente ottiene la raccolta di intestazioni dal `My.Request` oggetto e viene utilizzato il `My.Response` oggetto da scrivere la pagina ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Web.HttpRequest>
- [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
