---
title: Utilizzo efficiente dei tipi di dati
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 621dec7537e9c993024e271b96ab8706baf89885
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350114"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Utilizzo efficiente dei tipi di dati (Visual Basic)
Le variabili e le variabili non dichiarate dichiarate senza un tipo di dati vengono assegnate al tipo di dati `Object`. In questo modo è facile scrivere rapidamente i programmi, ma è possibile che vengano eseguiti più lentamente.

## <a name="strong-typing"></a>Tipizzazione forte
 Specificare i tipi di dati per tutte le variabili è noto come tipizzazione *forte*. L'uso di tipizzazione forte presenta diversi vantaggi:

- Abilita il supporto IntelliSense per le variabili. In questo modo è possibile visualizzare le relative proprietà e altri membri durante la digitazione nel codice.

- Sfrutta i vantaggi del controllo dei tipi del compilatore. Questa operazione intercetta le istruzioni che possono avere esito negativo in fase di esecuzione a causa di errori come l'overflow. Rileva inoltre le chiamate ai metodi su oggetti che non li supportano.

- Questo comporta un'esecuzione più rapida del codice.

## <a name="most-efficient-data-types"></a>Tipi di dati più efficienti
 Per le variabili che non contengono mai frazioni, i tipi di dati integrali sono più efficienti dei tipi non integrali. In Visual Basic, `Integer` e `UInteger` sono i tipi numerici più efficienti.

 Per i numeri frazionari, `Double` è il tipo di dati più efficiente, perché i processori sulle piattaforme correnti eseguono operazioni a virgola mobile con precisione doppia. Tuttavia, le operazioni con `Double` non sono altrettanto veloci dei tipi integrali, ad esempio `Integer`.

## <a name="specifying-data-type"></a>Specifica del tipo di dati
 Utilizzare l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) per dichiarare una variabile di un tipo specifico. È possibile specificare contemporaneamente il relativo livello di accesso tramite la parola chiave [public](../../../../visual-basic/language-reference/modifiers/public.md), [protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)o [private](../../../../visual-basic/language-reference/modifiers/private.md) , come nell'esempio seguente.

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>Conversione di caratteri
 Le funzioni `AscW` e `ChrW` funzionano in Unicode. È consigliabile utilizzarle in modo da `Asc` e `Chr`, che devono essere convertite all'interno e all'esterno di Unicode.

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati numerici](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Utilizzo di IntelliSense](/visualstudio/ide/using-intellisense)
