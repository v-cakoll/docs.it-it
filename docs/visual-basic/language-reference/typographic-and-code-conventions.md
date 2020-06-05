---
title: Convenzioni tipografiche e di scrittura del codice
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 0e36d9d61b0dd2701210ce614d15fd38f08f5401
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401355"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenzioni tipografiche e di scrittura del codice (Visual Basic)

Visual Basic documentazione utilizza le convenzioni tipografiche e di codice seguenti.  
  
## <a name="typographic-conventions"></a>Convenzioni tipografiche  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Le parole chiave specifiche del linguaggio e i membri di runtime hanno lettere maiuscole iniziali e sono formattati come illustrato in questo esempio.|  
|**SmallProject**, **buttoncollection**|Le parole e le frasi a cui viene richiesto il tipo sono formattate come illustrato in questo esempio.|  
|[Istruzione Module](statements/module-statement.md)|I collegamenti che è possibile fare clic per passare a un'altra pagina della guida sono formattati come illustrato in questo esempio.|  
|*Object*, *variablename*,`argumentList`|I segnaposto per le informazioni fornite vengono formattati come illustrato in questo esempio.|  
|[Shadows], [ *espressione* ]|Nella sintassi gli elementi facoltativi sono racchiusi tra parentesi quadre.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Nella sintassi, quando è necessario effettuare una scelta tra due o più elementi, gli elementi sono racchiusi tra parentesi graffe e separati da barre verticali.<br /><br /> È necessario selezionarne uno, e solo uno, degli elementi.|  
|[ `Protected` &#124; `Friend` ]|Nella sintassi, quando è possibile scegliere tra due o più elementi, gli elementi sono racchiusi tra parentesi quadre e separati da barre verticali.<br /><br /> È possibile selezionare qualsiasi combinazione degli elementi o nessun elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|Nella sintassi, quando è possibile selezionare non più di un elemento, ma è anche possibile omettere completamente gli elementi, gli elementi sono racchiusi tra parentesi quadre racchiusi tra parentesi graffe e separati da barre verticali.|  
|*memberName*1, *memberName*2, *memberName*3|Più istanze dello stesso segnaposto sono differenziate dagli indici, come illustrato nell'esempio.|  
|*Nomemembro1*<br /><br /> ...<br /><br /> *memberNameN*|Nella sintassi, i puntini di sospensione (...) vengono utilizzati per indicare un numero indefinito di elementi del tipo immediatamente davanti ai puntini di sospensione.<br /><br /> Nel codice i puntini di sospensione indicano il codice omesso per motivi di chiarezza.|  
|ESC, INVIO|I nomi delle chiavi e le sequenze di chiavi sulla tastiera vengono visualizzati in lettere maiuscole.|  
|ALT+F1|Quando vengono visualizzati i segni più (+) tra i nomi delle chiavi, è necessario mantenere premuto un tasto mentre si preme l'altro. ALT + F1, ad esempio, consente di mantenere premuto il tasto ALT mentre si preme il tasto F1.|  
  
## <a name="code-conventions"></a>Convenzioni del codice  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Gli esempi di codice vengono visualizzati in un tipo di carattere a passo fisso e sono formattati come illustrato in questo esempio.|  
|L'istruzione precedente imposta il valore di `sampleString` su "Hello, World!"|Gli elementi di codice nel testo esplicativo sono visualizzati in un tipo di carattere a passo fisso, come illustrato in questo esempio.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|I commenti del codice sono introdotti da un apostrofo (') o dalla parola chiave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Uno spazio seguito da un carattere di sottolineatura (_) alla fine di una riga indica che l'istruzione continua nella riga seguente.|  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti al linguaggio Visual Basic](index.md)
- [Parole chiave](keywords/index.md)
- [Membri della libreria di runtime di Visual Basic](runtime-library-members.md)
- [Convenzioni di denominazione di Visual Basic](../programming-guide/program-structure/naming-conventions.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Commenti nel codice](../programming-guide/program-structure/comments-in-code.md)
