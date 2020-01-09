---
title: Set di caratteri e marshalling - .NET
description: Informazioni su come i diversi valori di CharSet possono modificare il modo in cui .NET effettua il marshalling dei dati in codice nativo.
ms.date: 01/18/2019
ms.openlocfilehash: 4be4bd5a968eb5c0d6959a0f378ee1223ed906ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706387"
---
# <a name="charsets-and-marshaling"></a>Set di caratteri e marshalling

Il modo in cui viene eseguito il marshalling dei valori `char`, degli oggetti `string` e degli oggetti `System.Text.StringBuilder` dipende dal valore del campo `CharSet` per P/Invoke o la struttura. È possibile impostare il `CharSet` di P/Invoke, impostando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al momento della dichiarazione di P/Invoke. Per impostare il `CharSet` per un tipo, impostare il campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> nella dichiarazione di classe o struct. Quando questi campi attributo non vengono impostati, dipende dal compilatore del linguaggio determinare quale `CharSet` usare. C#e Visual Basic usare il set di caratteri <xref:System.Runtime.InteropServices.CharSet.Ansi> per impostazione predefinita.

La tabella seguente illustra il mapping tra ogni set di caratteri e la rappresentazione di un carattere o una stringa quando sottoposti a marshalling con tale set di caratteri:

| Valore di `CharSet` | Portale di            | .NET Core 2.2 e versioni precedenti in Unix | .NET core 3.0 e versioni successive e Mono in Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` ([tabella codici Windows (ANSI)](/windows/win32/intl/code-pages) predefinita del sistema)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Automatico            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Assicurarsi di conoscere la rappresentazione prevista dalla rappresentazione nativa quando si seleziona il set di caratteri.
