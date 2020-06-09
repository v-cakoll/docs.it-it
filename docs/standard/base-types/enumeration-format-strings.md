---
title: Stringhe di formato di enumerazione
description: Creare stringhe di formato di enumerazione usando il metodo Enum. ToString in .NET. Formattare i valori numerici, esadecimali o stringa dei membri dell'enumerazione.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: 825357cf4a56132dae0870972d316eff89b0c94f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84583427"
---
# <a name="enumeration-format-strings"></a>Stringhe di formato di enumerazione

È possibile usare il metodo <xref:System.Enum.ToString%2A?displayProperty=nameWithType> per creare un nuovo oggetto stringa che rappresenti il valore numerico, esadecimale o stringa di un membro di enumerazione. Questo metodo accetta una delle stringhe di formattazione di enumerazione per specificare il valore che si vuole venga restituito.

Nella tabella che segue sono elencate le stringhe di formattazione di enumerazione e i valori da esse restituiti. In questi identificatori di formato non viene fatta distinzione tra maiuscole e minuscole.

## <a name="g-or-g"></a>G o g

Visualizza la voce di enumerazione sotto forma di valore di stringa, se possibile; in caso contrario, visualizza il valore intero dell'istanza corrente. Se l'enumerazione viene definita con l'attributo **Flags** impostato, i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole. Se l'attributo **Flags** non è impostato, verrà visualizzato un valore non valido come voce numerica. L'esempio seguente illustra l'identificatore di formato G.

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a>F o f

Visualizza la voce di enumerazione come valore di stringa, se possibile. Se il valore può essere visualizzato interamente come somma delle voci nell'enumerazione (anche se l'attributo **Flags** è assente), i valori di stringa di ogni voce valida vengono concatenati tra loro, separati da virgole. Se non è possibile determinare completamente il valore sulla base delle voci di enumerazione, il valore verrà formattato sotto forma di valore intero. L'esempio seguente illustra l'identificatore di formato F.

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a>D o d

Visualizza la voce di enumerazione come valore intero nella rappresentazione più breve possibile. L'esempio seguente illustra l'identificatore di formato D.

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a>X o x

Visualizza la voce di enumerazione come valore esadecimale. Il valore viene rappresentato con zeri inziali, se necessario, per garantire che la stringa del risultato abbia due caratteri per ogni byte nel [tipo numerico sottostante](xref:System.Enum.GetUnderlyingType%2A) del tipo di enumerazione. L'esempio seguente illustra l'identificatore di formato X. Nell'esempio il tipo sottostante di <xref:System.ConsoleColor> e <xref:System.IO.FileAttributes> è <xref:System.Int32> o un numero intero a 32 bit (o 4 byte) che produce una stringa del risultato di 8 caratteri.

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a>Esempio

L'esempio seguente definisce un'enumerazione denominata `Colors` costituita dalle tre voci `Red`, `Blue` e `Green`.

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

Dopo aver definito l'enumerazione è possibile dichiararne un'istanza nel modo seguente.

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

Sarà quindi possibile usare il metodo `Color.ToString(System.String)` per visualizzare il valore di enumerazione in modi diversi, a seconda dell'identificatore di formato passato.

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a>Vedere anche

- [Formattazione di tipi](formatting-types.md)
