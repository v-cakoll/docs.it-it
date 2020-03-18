---
title: Caratteri di escape nelle espressioni regolari .NET
description: Informazioni sui caratteri speciali e i caratteri di escape nelle espressioni regolari .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unescaped characters
- replacement patterns
- characters, escapes
- regular expressions, character escapes
- escape characters
- .NET Framework regular expressions, character escapes
- constructs, character escapes
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
ms.openlocfilehash: 82e60b3cb5eb777d48219209550367642f78d8c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711428"
---
# <a name="character-escapes-in-regular-expressions"></a>Caratteri di escape nelle espressioni regolari
La barra rovesciata (\\) in un'espressione regolare indica una delle situazioni seguenti:  
  
- Il carattere che segue è un carattere speciale, come illustrato nella tabella nella sezione seguente. Ad esempio, `\b` è un ancoraggio che indica che una corrispondenza di un'espressione regolare deve iniziare sul confine di una parola, `\t` rappresenta un carattere di tabulazione e `\x020` rappresenta uno spazio.  
  
- Un carattere che altrimenti verrebbe interpretato come un costrutto di linguaggio non di escape deve essere interpretato letteralmente. Ad esempio, una parentesi graffa (`{`) segna l'inizio della definizione di un quantificatore, ma una barra rovesciata seguita da una parentesi graffa (`\{`) indica che il motore delle espressioni regolari deve trovare la corrispondenza con la parentesi graffa. Analogamente, una singola barra rovesciata segna l'inizio di un costrutto di linguaggio di escape, ma due barre rovesciate (`\\`) indicano che il motore delle espressioni regolari deve trovare la corrispondenza con la barra rovesciata.  
  
> [!NOTE]
> Le sequenze di caratteri di escape vengono riconosciute nei modelli di espressioni regolari, ma non nei modelli di sostituzione.  
  
## <a name="character-escapes-in-net"></a>Caratteri di escape in .NET  
 La tabella seguente elenca i caratteri di escape supportati dalle espressioni regolari in .NET.  
  
|Carattere o sequenza|Descrizione|  
|---------------------------|-----------------|  
|Tutti i caratteri eccetto i seguenti:<br /><br /> . $ ^ { [ ( &#124; ) * + ? \ |I caratteri diversi da quelli elencati nella colonna **Carattere o sequenza** non hanno un significato speciale nelle espressioni regolari, ma corrispondono a se stessi.<br /><br /> I caratteri inclusi nella colonna **Carattere o sequenza** sono elementi speciali del linguaggio di espressioni regolari. Per associarli in un'espressione regolare, è necessario essere preceduti dal carattere di escape o inclusi in un gruppo di [caratteri positivi.](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) Ad esempio, l'espressione regolare `\$\d+` o `[$]\d+` trova la corrispondenza con "$1200".|  
|`\a`|Corrisponde a un carattere di controllo del segnale acustico di avviso, `\u0007`.|  
|`\b`|In `[`una *character_group* `]` classe di caratteri, corrisponde a un backspace, `\u0008`.  (Vedere [classi di caratteri](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).) All'esterno di `\b` una classe di caratteri, è un ancoraggio che corrisponde a un confine di parola. Vedere [Ancoraggi](../../../docs/standard/base-types/anchors-in-regular-expressions.md).|  
|`\t`|Corrisponde a un carattere di tabulazione, `\u0009`.|  
|`\r`|Corrisponde a un carattere di ritorno a capo, `\u000D`. Si noti che `\r` non equivale al carattere di nuova riga, `\n`.|  
|`\v`|Corrisponde a un carattere di tabulazione verticale, `\u000B`.|  
|`\f`|Corrisponde a un carattere di avanzamento carta, `\u000C`.|  
|`\n`|Corrisponde a una nuova riga, `\u000A`.|  
|`\e`|Corrisponde a un carattere di escape, `\u001B`.|  
|`\` *nnn*|Corrisponde a un carattere ASCII, dove *nnn* è costituito da due o tre cifre che rappresentano il codice di carattere ottale. Ad esempio, `\040` rappresenta un carattere di spazio. Questo costrutto viene interpretato come un backreference se è costituito solo da una cifra, ad esempio `\2` o se corrisponde al numero di un gruppo di acquisizione. Vedere [Costrutti di backreference](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).|  
|`\x`*nn*|Corrisponde a un carattere ASCII dove *nn* è un codice carattere esadecimale a due cifre.|  
|`\c`*X (in* vi o|Corrisponde a un carattere di controllo ASCII, dove X è la lettera del carattere di controllo. Ad esempio, `\cC` corrisponde a CTRL-C.|  
|`\u` *nnnn*|Corrisponde a un'unità di codice UTF-16 il cui valore è l'esadecimale *nnnn*. **Nota:** la sequenza di caratteri di escape Perl 5 usata per specificare Unicode non è supportata da .NET. Il formato di escape carattere Perl 5 ha il `\x{` *####* `…}`formato , dove *####* `…` è una serie di cifre esadecimali. Usare invece `\u`*nnnn*.|  
|`\`|Quando è seguito da un carattere non riconosciuto come carattere di escape, corrisponde a tale carattere. Ad esempio, `\*` corrisponde a un asterisco (*) ed equivale a `\x2A`.|  
  
## <a name="an-example"></a>Esempio  
 L'esempio seguente illustra l'uso di una sequenza di caratteri di escape in un'espressione regolare. Viene analizzata una stringa contenente i nomi delle più grandi città del mondo e la relativa popolazione nel 2009. Ogni nome di città è separato dalla relativa popolazione da un carattere di tabulazione (`\t`) o da una barra verticale (&#124; o `\u007c`). Le singole città e la relativa popolazione sono separate tra loro da un ritorno a capo e un avanzamento riga.  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 L'espressione regolare `\G(.+)[\t|\u007c](.+)\r?\n` viene interpretata come illustrato nella tabella seguente.  
  
|Modello|Descrizione|  
|-------------|-----------------|  
|`\G`|Inizia la corrispondenza dove termina l'ultima corrispondenza.|  
|`(.+)`|Trova la corrispondenza con qualsiasi carattere uno o più volte. Equivale al primo gruppo di acquisizione.|  
|`[\t\u007c]`|Trova la corrispondenza con un carattere di tabulazione (`\t`) o una barra verticale (&#124;).|  
|`(.+)`|Trova la corrispondenza con qualsiasi carattere uno o più volte. Equivale al secondo gruppo di acquisizione.|  
|`\r?\n`|Trova la corrispondenza con zero o una occorrenza di un ritorno a capo seguito da una nuova riga.|  
  
## <a name="see-also"></a>Vedere anche

- [Linguaggio delle espressioni regolari - Guida di riferimento rapidoRegular Expression Language - Quick Reference](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
