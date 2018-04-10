---
title: extern alias (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4e995586c08659853538726a12679770cd1ada37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="extern-alias-c-reference"></a>extern alias (Riferimenti per C#)
È necessario far riferimento a due versioni di assembly che dispongono degli stessi nomi di tipo completi. Ad esempio, potrebbe essere necessario usare due o più versioni di un assembly nella stessa applicazione. Con un alias di assembly esterno, è possibile eseguire il wrapping degli spazi dei nomi di ogni assembly all'interno degli spazi dei nomi a livello radice denominati dall'alias, consentendone l'utilizzo nello stesso file.  
  
> [!NOTE]
>  La parola chiave [extern](../../../csharp/language-reference/keywords/extern.md) viene anche usata come modificatore di metodo, che dichiara un metodo scritto in codice non gestito.  
  
 Per far riferimento a due assembly con gli stessi nomi di tipo completi, è necessario specificare un alias al prompt dei comandi, come indicato di seguito:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 In questo modo vengono creati gli alias extern `GridV1` e `GridV2`. Per usare questi alias all'interno di un programma, far riferimento a essi tramite la parola chiave `extern`. Ad esempio:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Ogni dichiarazione di alias extern introduce uno spazio dei nomi aggiuntivo a livello radice che affianca lo spazio dei nomi globale, ma non si trova al suo interno. In questo modo, è possibile far riferimento ai tipi di ogni assembly senza ambiguità, usando il nome completo che dispone di una radice nell'alias dello spazio dei nomi appropriato.  
  
 Nell'esempio precedente, l'oggetto `GridV1::Grid` rappresenta il controllo griglia dell'oggetto `grid.dll`, e `GridV2::Grid` rappresenta il controllo griglia dell'oggetto `grid20.dll`.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [Operatore ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [-reference (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
