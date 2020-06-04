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
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415492"
---
# <a name="user-defined-data-type"></a>Tipo di dati definito dall'utente

Include i dati in un formato definito dall'utente. L' `Structure` istruzione definisce il formato.

Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT). La versione corrente espande il tipo definito dall'utente a una *struttura*. Una struttura è una concatenazione di uno o più *membri* di diversi tipi di dati. Visual Basic considera una struttura come una singola unità, sebbene sia anche possibile accedere singolarmente ai relativi membri.

## <a name="remarks"></a>Commenti

Definire e usare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità o quando nessuno dei tipi di dati elementari soddisfa le proprie esigenze.

Il valore predefinito di un tipo di dati della struttura è costituito dalla combinazione dei valori predefiniti di ognuno dei relativi membri.

## <a name="declaration-format"></a>Formato della dichiarazione

Una dichiarazione di struttura inizia con l' [istruzione Structure](../statements/structure-statement.md) e termina con l' `End Structure` istruzione. L' `Structure` istruzione fornisce il nome della struttura, che è anche l'identificatore del tipo di dati che la struttura sta definendo. Altre parti del codice possono usare questo identificatore per dichiarare variabili, parametri e valori restituiti della funzione in modo che siano del tipo di dati della struttura.

Le dichiarazioni tra le `Structure` istruzioni e `End Structure` definiscono i membri della struttura.

## <a name="member-access-levels"></a>Livelli di accesso ai membri

È necessario dichiarare ogni membro usando un' [istruzione Dim](../statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [public](../modifiers/public.md), [Friend](../modifiers/friend.md)o [private](../modifiers/private.md). Se si usa un' `Dim` istruzione, il livello di accesso predefinito è public.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Consumo di memoria.** Come per tutti i tipi di dati compositi, non è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura aggiungendo le allocazioni di archiviazione nominale dei relativi membri. Inoltre, non è possibile presupporre in modo sicuro che l'ordine di archiviazione in memoria sia uguale all'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare l' <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo all' `Structure` istruzione.

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic tipi di struttura.

- **Conversioni.** Non viene eseguita alcuna conversione automatica da o verso qualsiasi tipo di dati della struttura. È possibile definire gli operatori di conversione sulla struttura usando l' [istruzione Operator](../statements/operator-statement.md)ed è possibile dichiarare ogni operatore di conversione come `Widening` o `Narrowing` .

- **Digitare i caratteri.** I tipi di dati della struttura non hanno un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di framework.** Nessun tipo corrispondente nell'.NET Framework. Tutte le strutture ereditano dalla classe .NET Framework <xref:System.ValueType?displayProperty=nameWithType> , ma nessuna struttura specifica corrisponde a <xref:System.ValueType?displayProperty=nameWithType> .

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
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Istruzione Structure](../statements/structure-statement.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
