---
title: Set di caratteri e marshalling - .NET
description: Informazioni su come i diversi valori di CharSet possono modificare il modo in cui .NET effettua il marshalling dei dati in codice nativo.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2ff6c485906db481cb5236f83e885ba9fd46450b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411407"
---
# <a name="charsets-and-marshalling"></a>Set di caratteri e marshalling

Il modo in cui viene effettuato il marshalling dei valori `char`, degli oggetti `string` e degli oggetti `System.Text.StringBuilder` dipende dal valore del campo `CharSet` per P/Invoke o la struttura. È possibile impostare il `CharSet` di P/Invoke, impostando il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> al momento della dichiarazione di P/Invoke. Per impostare il `CharSet` per una struttura, impostare il campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> nella dichiarazione dello struct. Quando questi campi attributo non vengono impostati, dipende dal compilatore del linguaggio determinare quale `CharSet` usare. C# usa il set di caratteri <xref:System.Runtime.InteropServices.CharSet.Ansi> per impostazione predefinita.

La tabella seguente mostra il mapping tra ogni set di caratteri e la rappresentazione di un carattere o una stringa quando sottoposto a marshalling con tale set di caratteri:

| CharSet | Windows | Unix | Mono in Unix |
|---------|---------|-------|-------|
| Ansi    | `char` (ANSI)  | `char` (ANSI in macOS, UTF-8 in Linux) | `char` (UTF-8) |
| Unicode | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char16_t` (UTF-16) |
| Auto | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char` (UTF-8) |

Assicurarsi di conoscere la rappresentazione prevista dalla rappresentazione nativa quando si seleziona il set di caratteri.
