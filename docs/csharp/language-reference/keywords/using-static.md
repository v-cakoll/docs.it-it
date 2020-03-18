---
title: Direttiva using static - Riferimenti per C#
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
ms.openlocfilehash: 55847aceb9fdf032ba533b82ee59be53761fa2c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712949"
---
# <a name="using-static-directive-c-reference"></a>Direttiva using static (Riferimenti per C#)

La direttiva `using static` consente di definire un tipo i cui membri statici e i tipi nidificati sono accessibili senza specificare un nome di tipo. La relativa sintassi è la seguente:

```csharp
using static <fully-qualified-type-name>;
```

dove *fully-qualified-type-name* è il nome del tipo i cui membri statici e i tipi nidificati possono essere usati come riferimento senza specificare un nome di tipo. Se non si specifica un nome di tipo completo (il nome completo dello spazio dei nomi con il nome del tipo), C# genera l'errore del compilatore [CS0246](../compiler-messages/cs0246.md): "Impossibile trovare il nome del tipo o dello spazio dei nomi 'type/namespace' (probabilmente manca una direttiva using o un riferimento a un assembly)".

La direttiva `using static` si applica a qualsiasi tipo che includa membri statici (o tipi nidificati), anche qualora siano presenti membri di istanza. Tuttavia, i membri di istanza possono essere chiamati solo tramite l'istanza del tipo.

La direttiva `using static` è stata introdotta in C# 6.

## <a name="remarks"></a>Osservazioni

Quando si chiama un membro statico si fornisce in genere il nome del tipo e il nome del membro. Immettere ripetutamente lo stesso nome di tipo per chiamare i membri del tipo può generare codice troppo dettagliato e incomprensibile. Ad esempio, la seguente definizione di una classe `Circle` fa riferimento a un numero di membri della classe <xref:System.Math>.

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

Eliminando la necessità di fare riferimento in modo esplicito alla classe <xref:System.Math> ogni volta che si fa riferimento a un membro, la direttiva `using static` genera un codice più chiaro:

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

`using static` importa solo i membri statici accessibili e i tipi annidati dichiarati nel tipo specificato.  I membri ereditati non vengono importati.  È possibile eseguire l'importazione da qualsiasi tipo denominato con una direttiva using static, inclusi i moduli Visual Basic.  Se nei metadati vengono visualizzate funzioni di primo livello F# come membri statici di un tipo denominato il cui nome è un identificatore C# valido, le funzioni F# possono essere importate.

 `using static` crea metodi di estensione dichiarati nel tipo specificato disponibile per la ricerca del metodo di estensione.  Tuttavia, i nomi dei metodi di estensione non vengono importati nell'ambito del riferimento non qualificato nel codice.

 I metodi con lo stesso nome importati da tipi diversi tramite direttive `using static` diverse nella stessa unità di compilazione o nello stesso spazio dei nomi costituiscono un gruppo di metodi.  La risoluzione dell'overload in questi gruppi di metodi segue le normali regole C#.

## <a name="example"></a>Esempio

L'esempio seguente usa la direttiva `using static` per rendere i membri statici della classe <xref:System.Console>, <xref:System.Math> e <xref:System.String> disponibili senza dover specificare il nome del tipo.

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

Nell'esempio la direttiva `using static` può anche essere stata applicata al tipo <xref:System.Double>. In questo caso sarebbe stato possibile chiamare il metodo <xref:System.Double.TryParse(System.String,System.Double@)> senza specificare un nome di tipo. Ciò crea tuttavia codice meno leggibile, poiché è necessario controllare le istruzioni `using static` per quale metodo `TryParse` di tipo numerico viene chiamato.

## <a name="see-also"></a>Vedere anche

- [using (direttiva)](using-directive.md)
- [Guida di riferimento a C](../index.md)
- [Parole chiave di C#](index.md)
- [Uso degli spazi dei nomi](../../programming-guide/namespaces/using-namespaces.md)
- [Spazi dei nomi](../../programming-guide/namespaces/index.md)
