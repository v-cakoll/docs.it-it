---
title: Set di caratteri e marshalling - .NET
description: Informazioni su come i diversi valori di CharSet possono modificare il modo in cui .NET effettua il marshalling dei dati in codice nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: c50c58ad639b1efb29c13e5124fe3c32e8af96fc
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063328"
---
# <a name="charsets-and-marshaling"></a>Set di caratteri e marshalling

Il modo in cui viene eseguito il marshalling dei valori `char`, degli oggetti `string` e degli oggetti `System.Text.StringBuilder` dipende dal valore del campo `CharSet` per P/Invoke o la struttura. È possibile impostare il `CharSet` di P/Invoke, impostando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al momento della dichiarazione di P/Invoke. Per impostare il `CharSet` per una struttura, impostare il campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> nella dichiarazione dello struct. Quando questi campi attributo non vengono impostati, dipende dal compilatore del linguaggio determinare quale `CharSet` usare. Per impostazione predefinita, C# e VB usano il set di caratteri <xref:System.Runtime.InteropServices.CharSet.Ansi>.

La tabella seguente illustra il mapping tra ogni set di caratteri e la rappresentazione di un carattere o una stringa quando sottoposti a marshalling con tale set di caratteri:

| Valore di `CharSet` | WINDOWS            | .NET Core 2.2 e versioni precedenti in Unix | .NET core 3.0 e versioni successive e Mono in Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (ANSI)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Auto            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Assicurarsi di conoscere la rappresentazione prevista dalla rappresentazione nativa quando si seleziona il set di caratteri.
