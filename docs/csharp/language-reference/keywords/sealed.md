---
title: sealed (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8248b451f0431286fdaba3583fc2031eb6cdbcd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sealed-c-reference"></a>sealed (Riferimenti per C#)
Quando applicato a una classe, il modificatore `sealed` impedisce che altre classi ereditino da esso. Nell'esempio seguente, la classe `B` eredita dalla classe `A`, ma nessuna classe può ereditare dalla classe `B`.  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 È anche possibile usare il modificatore `sealed` su un metodo o su una proprietà che esegue l'override di un metodo o di una proprietà virtuale in una classe di base. In questo modo è possibile consentire alle classi di derivare dalla classe e impedire l'override di proprietà o metodi virtuali specifici.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `Z` eredita da `Y` ma `Z` non può eseguire l'override della funzione virtuale `F` dichiarata in `X` e bloccata in `Y`.  
  
 [!code-csharp[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 Quando si definiscono nuovi metodi o proprietà in una classe, è possibile impedire alle classi derivate di eseguire l'override non dichiarandole come [virtuali](../../../csharp/language-reference/keywords/virtual.md).  
  
 È un errore usare il modificatore [abstract](../../../csharp/language-reference/keywords/abstract.md) con una classe sealed, poiché la classe astratta deve essere ereditata da una classe che fornisce un'implementazione dei metodi o delle proprietà astratti.  
  
 Quando applicato a un metodo o a una proprietà, il modificatore `sealed` deve sempre essere usato con [override](../../../csharp/language-reference/keywords/override.md).  
  
 Poiché gli struct sono sealed in modo implicito, non possono essere ereditati.  
  
 Per altre informazioni, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Per altri esempi, vedere [Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 Nell'esempio precedente è possibile ereditare dalla classe sealed tramite l'istruzione seguente:  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 Il risultato è un messaggio di errore:  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a>Note  
 Per determinare se bloccare una classe, proprietà o metodo, è consigliabile in genere considerare i due punti seguenti:  
  
-   I potenziali vantaggi di cui le classi derivate possono usufruire grazie alla possibilità di personalizzare la classe.  
  
-   La possibilità che le classi derivate possono modificare le classi in uso in modo tale che non funzionino più correttamente o come previsto.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
 [override](../../../csharp/language-reference/keywords/override.md)  
 [virtual](../../../csharp/language-reference/keywords/virtual.md)
