---
title: Out (modificatore generico)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 0460015b44971fa638dba47183690ffcc89ca55f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351419"
---
# <a name="out-generic-modifier-visual-basic"></a>Out (modificatore generico) (Visual Basic)

Per i parametri di tipo generico, la parola chiave `Out` specifica che il tipo è covariante.

## <a name="remarks"></a>Note

La covarianza consente di usare un tipo più derivato di quello specificato dal parametro generico. Ciò consente la conversione implicita di classi che implementano interfacce varianti e la conversione implicita di tipi delegati.

Per altre informazioni, vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Regole

È possibile usare la parola chiave `Out` in interfacce e delegati generici.

In un'interfaccia generica un parametro di tipo può essere dichiarato covariante se soddisfa le condizioni seguenti:

- Il parametro di tipo viene usato solo come tipo restituito di metodi di interfaccia e non viene usato come tipo di argomenti del metodo.

    > [!NOTE]
    > Esiste un'eccezione a questa regola. Se in un'interfaccia covariante è presente un delegato generico controvariante come parametro del metodo, è possibile usare il tipo covariante come parametro di tipo generico per questo delegato. Per altre informazioni sui delegati generici covarianti e controvarianti, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- Il parametro di tipo non viene usato come vincolo generico per i metodi di interfaccia.

In un delegato generico, un parametro di tipo può essere dichiarato covariante se viene usato solo come tipo restituito del metodo e non usato per gli argomenti del metodo.

La covarianza e la controvarianza sono supportate per i tipi di riferimento, ma non per i tipi di valore.

In Visual Basic non è possibile dichiarare gli eventi nelle interfacce covariante senza specificare il tipo delegato. Inoltre, le interfacce covariante non possono avere classi, enumerazioni o strutture annidate, ma possono avere interfacce nidificate.

## <a name="behavior"></a>Comportamento

Un'interfaccia che dispone di un parametro di tipo covariante consente ai metodi di restituire tipi più derivati di quelli specificati dal parametro di tipo. Poiché, ad esempio, in .NET Framework 4, nell'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, il tipo T è covariante, è possibile assegnare un oggetto di tipo `IEnumerable(Of String)` a un oggetto di tipo `IEnumerable(Of Object)` senza usare alcun metodo di conversione speciale.

A un delegato covariante può essere assegnato un altro delegato dello stesso tipo, ma con un parametro di tipo generico più derivato.

## <a name="example"></a>Esempio

L'esempio seguente illustra come dichiarare, estendere e implementare un'interfaccia generica covariante. L'esempio descrive anche come usare la conversione implicita per le classi che implementano un'interfaccia covariante.

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a>Esempio

L'esempio seguente illustra come dichiarare, creare un'istanza e richiamare un delegato generico covariante. Viene inoltre illustrato come è possibile utilizzare la conversione implicita per i tipi delegati.

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a>Vedere anche

- [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
