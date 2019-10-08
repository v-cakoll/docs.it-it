---
title: In (modificatore generico)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004878"
---
# <a name="in-generic-modifier-visual-basic"></a>In (modificatore generico) (Visual Basic)

Per i parametri di tipo generico, la parola chiave `In` specifica che il parametro di tipo è controvariante.

## <a name="remarks"></a>Note

La controvarianza consente di usare un tipo meno derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.

Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Regole

È possibile usare la parola chiave `In` in interfacce e delegati generici.
  
Un parametro di tipo può essere dichiarato controvariante in un'interfaccia o in un delegato generico se viene usato solo come tipo di argomenti del metodo e non viene usato come tipo restituito del metodo. i parametri `ByRef` non possono essere covarianti o controvarianti.

Covarianza e controvarianza sono supportate per i tipi di riferimento e non sono supportate per i tipi di valore.

In Visual Basic non è possibile dichiarare eventi in interfacce controvarianti senza specificare il tipo delegato. Inoltre, le interfacce controvarianti non possono avere classi, enumerazioni o strutture annidate, ma possono avere interfacce nidificate.

## <a name="behavior"></a>Comportamento

Un'interfaccia che dispone di un parametro di tipo controvariante consente ai metodi di accettare argomenti di tipi meno derivati di quelli specificati dal parametro di tipo di interfaccia. Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IComparer%601>, il tipo T è controvariante, è possibile assegnare un oggetto del tipo `IComparer(Of Person)` a un oggetto del tipo `IComparer(Of Employee)` senza usare alcun metodo di conversione speciale se `Employee` eredita da `Person`.

A un delegato controvariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico meno derivato.

## <a name="example---contravariant-generic-interface"></a>Esempio: interfaccia generica controvariante

L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica controvariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano quest'interfaccia.

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a>Esempio: delegato generico controvariante

L'esempio seguente illustra come dichiarare, creare un'istanza e chiamare un delegato generico controvariante. Illustra anche come convertire in modo implicito un tipo delegato.

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a>Vedere anche

- [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Out](out-generic-modifier.md)
