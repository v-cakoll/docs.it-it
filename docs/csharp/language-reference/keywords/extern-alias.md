---
title: extern alias - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 86202333484933d7449b0c4d8c5a3f1a63cd7775
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713552"
---
# <a name="extern-alias-c-reference"></a>extern alias (Riferimenti per C#)
È necessario far riferimento a due versioni di assembly che dispongono degli stessi nomi di tipo completi. Ad esempio, potrebbe essere necessario usare due o più versioni di un assembly nella stessa applicazione. Con un alias di assembly esterno, è possibile eseguire il wrapping degli spazi dei nomi di ogni assembly all'interno degli spazi dei nomi a livello radice denominati dall'alias, consentendone l'utilizzo nello stesso file.  
  
> [!NOTE]
> La parola chiave [extern](./extern.md) viene anche usata come modificatore di metodo, che dichiara un metodo scritto in codice non gestito.  
  
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

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [:: Operatore](../operators/namespace-alias-qualifier.md)
- [-reference (opzioni del compilatore C](../compiler-options/reference-compiler-option.md)
