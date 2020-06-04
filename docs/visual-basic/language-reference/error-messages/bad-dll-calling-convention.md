---
title: Convenzione di chiamata DLL non valida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: a60e44ce92b1805b0a5a6f1d4ce397c295eef202
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409881"
---
# <a name="bad-dll-calling-convention"></a>Convenzione di chiamata DLL non valida
Gli argomenti passati a una libreria di collegamento dinamico (DLL) devono corrispondere esattamente a quelli previsti dalla routine. Le convenzioni di chiamata gestiscono il numero, il tipo e l'ordine degli argomenti. È possibile che il programma chiami una routine in una DLL a cui viene passato il tipo o il numero di argomenti errato.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che tutti i tipi di argomento condividano quelli specificati nella dichiarazione della routine che si sta chiamando.  
  
2. Assicurarsi di passare lo stesso numero di argomenti indicato nella dichiarazione della routine che si sta chiamando.  
  
3. Se la routine DLL prevede gli argomenti per valore, assicurarsi che `ByVal` sia specificato per gli argomenti nella dichiarazione per la routine.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../programming-guide/language-features/error-types.md)
- [Istruzione Call](../statements/call-statement.md)
- [Declare Statement](../statements/declare-statement.md)
