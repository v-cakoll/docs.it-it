---
title: in (Modificatore generico) (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84773fca826b5a25679f1385a11c51b590ea20f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="in-generic-modifier-c-reference"></a>in (Modificatore generico) (Riferimenti per C#)
Per i parametri di tipo generico, la parola chiave `in` specifica che il parametro di tipo è controvariante. È possibile usare la parola chiave `in` in interfacce e delegati generici.  
  
 La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati. Nei parametri di tipo generico la covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.  
  
 Un tipo può essere dichiarato controvariante in un'interfaccia o in un delegato generico se viene usato solo come tipo di argomenti del metodo e non come tipo restituito dal metodo. I parametri `Ref` e `out` non possono essere variant.  
  
 Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia. Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer(Of Person)` a un oggetto di tipo `IComparer(Of Employee)` senza usare alcun metodo di conversione speciale se `Employee` eredita `Person`.  
  
 A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.  
  
 Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante. Illustra anche come convertire in modo implicito un tipo delegato.  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)
