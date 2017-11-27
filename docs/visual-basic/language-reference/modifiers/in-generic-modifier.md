---
title: In (modificatore generico) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e9aab4fc361754cfd750ae68f04b36dce13d0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="in-generic-modifier-visual-basic"></a>In (modificatore generico) (Visual Basic)
Per i parametri di tipo generico, la parola chiave `In` specifica che il parametro di tipo è controvariante.  
  
## <a name="remarks"></a>Note  
 La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.  
  
 Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="rules"></a>Regole  
 È possibile usare la parola chiave `In` in interfacce e delegati generici.  
  
 Un parametro di tipo può essere dichiarato controvariante in un'interfaccia generica o delegato se viene utilizzata solo come tipo di argomenti del metodo e non come un tipo restituito del metodo. `ByRef`parametri non possono essere di tipo covarianti o controvariante.  
  
 Covarianza e controvarianza sono supportate per i tipi di riferimento e non è supportate per i tipi di valore.  
  
 In Visual Basic, è possibile dichiarare gli eventi nelle interfacce controvarianti senza specificare il tipo delegato. Inoltre, interfacce controvariante non è possibile avere, enumerazioni, strutture o classi annidate, ma può disporre di interfacce annidate.  
  
## <a name="behavior"></a>Comportamento  
 Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia. Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto di tipo `IComparer(Of Person)` a un oggetto di tipo `IComparer(Of Employee)` senza usare alcun metodo di conversione speciale se `Person` eredita `Employee`.  
  
 A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.  
  
 [!code-vb[vbVarianceKeywords#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante. Illustra anche come convertire in modo implicito un tipo delegato.  
  
 [!code-vb[vbVarianceKeywords#2](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/in-generic-modifier_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
