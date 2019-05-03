---
title: Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 04124ca044ad8dbff58f85230d7e10ea336d41e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751696"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a>Una chiamata a una proprietà o a un metodo non può includere un riferimento a un oggetto privato, né come argomento né come valore restituito
Di seguito sono riportate le cause possibili dell'errore:  
  
- Un client ha richiamato una proprietà o un metodo di un componente out-of-process e ha tentato di passare un riferimento a un oggetto privato come uno degli argomenti.  
  
- Un componente out-of-process ha richiamato un metodo di richiamata sul relativo client e ha tentato di passare un riferimento a un oggetto privato.  
  
- Un componente out-of-process ha tentato di passare un riferimento a un oggetto privato come argomento dell'evento che stava generando.  
  
- Un client ha tentato di assegnare un riferimento a un oggetto privato a un argomento `ByRef` dell'evento che stava gestendo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rimuovere il riferimento.  
  
## <a name="see-also"></a>Vedere anche

- [Private](../../../visual-basic/language-reference/modifiers/private.md)
