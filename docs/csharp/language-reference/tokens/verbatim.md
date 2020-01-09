---
title: '@ - Riferimenti per C#'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: a3446eceb0d3c415e36ea1d2c7d8d6d34f65350d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712416"
---
# <a name="-c-reference"></a>@ (Riferimenti per C#)

Il carattere speciale `@` funge da identificatore verbatim. Può essere usato nei seguenti modi:

1. Per abilitare le parole chiave di C# da usare come identificatori. Il carattere `@` precede un elemento di codice che il compilatore deve interpretare come identificatore piuttosto che come parola chiave di C#. Nell'esempio seguente il carattere `@` viene usato per definire un identificatore denominato `for` che verrà usato in un ciclo `for`.

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Per indicare che un valore letterale stringa deve essere interpretato come verbatim. Il carattere `@` in questa istanza definisce un *valore letterale stringa verbatim*. Le sequenze di escape semplici, ad esempio `"\\"` per una barra rovesciata, le sequenze di escape esadecimali, ad esempio `"\x0041"` per una A maiuscola, le sequenze di escape Unicode, ad esempio `"\u0041"` per una A maiuscola, vengono interpretate letteralmente. Solo una sequenza di escape per le virgolette doppie (`""`) non viene interpretata letteralmente e produce una virgoletta singola. Inoltre, in caso di una [stringa interpolata](interpolated.md) verbatim, le sequenze di escape con parentesi graffa (`{{` e `}}`) non vengono interpretate letteralmente; producono caratteri singoli di parentesi graffa. Nell'esempio seguente vengono definiti due percorsi di file identici, uno usando un valore letterale stringa normale e l'altro usando un valore letterale stringa verbatim. Questo è uno degli usi più comuni dei valori letterali stringa verbatim.

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   Nell'esempio seguente viene illustrato l'effetto della definizione di un valore letterale stringa normale e di un valore letterale stringa verbatim che contengono le sequenze di caratteri identiche.

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Per consentire al compilatore di distinguere tra gli attributi in caso di conflitto di denominazione. Un attributo è una classe che deriva da <xref:System.Attribute>. Il nome del relativo tipo in genere include il suffisso **Attribute**, anche se il compilatore non applica questa convenzione. È possibile fare riferimento all'attributo nel codice usando il nome completo del tipo, ad esempio `[InfoAttribute]`, o il nome abbreviato, ad esempio, `[Info]`. Tuttavia, si verifica un conflitto di denominazione se due nomi di tipo di attributo abbreviati sono identici e se un nome di tipo include il suffisso **Attribute** e l'altro no. Ad esempio, il codice seguente non viene compilato perché il compilatore non è in grado di determinare se l'attributo `Info` o `InfoAttribute` viene applicato alla classe `Example`. Per altre informazioni, vedere [CS1614](../compiler-messages/cs1614.md).

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Caratteri speciali di C#](./index.md)
