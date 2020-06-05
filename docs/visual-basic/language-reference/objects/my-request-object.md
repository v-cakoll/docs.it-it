---
title: Oggetto My.Request
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 38f510e2a3958761b902f37760069aa8d595ea8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372427"
---
# <a name="myrequest-object"></a>Oggetto My.Request
Ottiene l'oggetto <xref:System.Web.HttpRequest> per la pagina richiesta.  
  
## <a name="remarks"></a>Commenti  
 L'oggetto `My.Request` contiene informazioni sulla richiesta HTTP corrente.  
  
 L'oggetto `My.Request` è disponibile solo per le applicazioni ASP.NET.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuta la raccolta di intestazioni dall' `My.Request` oggetto e viene utilizzato l' `My.Response` oggetto per scriverlo nella pagina ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Web.HttpRequest>
- [Oggetto My.Response](my-response-object.md)
