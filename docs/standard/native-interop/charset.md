---
title: Set di caratteri e marshalling - .NET
description: Informazioni su come i diversi valori di CharSet possono modificare il modo in cui .NET effettua il marshalling dei dati in codice nativo.
ms.date: 01/18/2019
ms.openlocfilehash: 39566593aa38bacfa41b44a8af8cc2dfb294d766
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416109"
---
# <a name="charsets-and-marshaling"></a>Set di caratteri e marshalling

Il modo in cui viene eseguito il marshalling dei valori `char`, degli oggetti `string` e degli oggetti `System.Text.StringBuilder` dipende dal valore del campo `CharSet` per P/Invoke o la struttura. È possibile impostare il `CharSet` di P/Invoke, impostando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al momento della dichiarazione di P/Invoke. Per impostare `CharSet` per un tipo, impostare il <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> campo nella dichiarazione di classe o struct. Quando questi campi attributo non vengono impostati, dipende dal compilatore del linguaggio determinare quale `CharSet` usare. C# e Visual Basic usano il <xref:System.Runtime.InteropServices.CharSet.Ansi> set di caratteri per impostazione predefinita.

La tabella seguente illustra il mapping tra ogni set di caratteri e la rappresentazione di un carattere o una stringa quando sottoposti a marshalling con tale set di caratteri:

| Valore della proprietà `CharSet` | Windows            | .NET Core 2.2 e versioni precedenti in Unix | .NET core 3.0 e versioni successive e Mono in Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| `Ansi`          | `char` ([tabella codici Windows (ANSI)](/windows/win32/intl/code-pages) predefinita del sistema)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| `Unicode`       | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| `Auto`          | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Assicurarsi di conoscere la rappresentazione prevista dalla rappresentazione nativa quando si seleziona il set di caratteri.
