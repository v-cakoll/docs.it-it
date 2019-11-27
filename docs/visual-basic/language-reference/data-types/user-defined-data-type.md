---
title: Tipo di dati definito dall'utente
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 99eeb4b619f6bb23d00f8e449de953d41843f714
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343873"
---
# <a name="user-defined-data-type"></a>Tipo di dati definito dall'utente

Include i dati in un formato definito dall'utente. L'istruzione `Structure` definisce il formato.

Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT). La versione corrente espande il tipo definito dall'utente a una *struttura*. Una struttura è una concatenazione di uno o più *membri* di diversi tipi di dati. Visual Basic considera una struttura come una singola unità, sebbene sia anche possibile accedere singolarmente ai relativi membri.

## <a name="remarks"></a>Osservazioni

Definire e usare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità o quando nessuno dei tipi di dati elementari soddisfa le proprie esigenze.

Il valore predefinito di un tipo di dati della struttura è costituito dalla combinazione dei valori predefiniti di ognuno dei relativi membri.

## <a name="declaration-format"></a>Formato della dichiarazione

Una dichiarazione di struttura inizia con l' [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) e termina con l'istruzione `End Structure`. L'istruzione `Structure` fornisce il nome della struttura, che è anche l'identificatore del tipo di dati che la struttura sta definendo. Altre parti del codice possono usare questo identificatore per dichiarare variabili, parametri e valori restituiti della funzione in modo che siano del tipo di dati della struttura.

Le dichiarazioni tra le istruzioni `Structure` e `End Structure` definiscono i membri della struttura.

## <a name="member-access-levels"></a>Livelli di accesso ai membri

È necessario dichiarare ogni membro usando un' [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md)o [private](../../../visual-basic/language-reference/modifiers/private.md). Se si usa un'istruzione `Dim`, il livello di accesso predefinito è public.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Consumo di memoria.** Come per tutti i tipi di dati compositi, non è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura aggiungendo le allocazioni di archiviazione nominale dei relativi membri. Inoltre, non è possibile presupporre in modo sicuro che l'ordine di archiviazione in memoria sia uguale all'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> all'istruzione `Structure`.

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic tipi di struttura.

- **Conversioni.** Non viene eseguita alcuna conversione automatica da o verso qualsiasi tipo di dati della struttura. È possibile definire gli operatori di conversione sulla struttura usando l' [istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)ed è possibile dichiarare ogni operatore di conversione come `Widening` o `Narrowing`.

- **Digitare i caratteri.** I tipi di dati della struttura non hanno un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di Framework.** Nessun tipo corrispondente nell'.NET Framework. Tutte le strutture ereditano dalla classe .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, ma nessuna struttura specifica corrisponde a <xref:System.ValueType?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Nel paradigma seguente viene illustrato il contorno della dichiarazione di una struttura.

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a>Vedere anche

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
