---
title: Convenzioni tipografiche e di scrittura del codice (Visual Basic)
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
ms.openlocfilehash: eb7a33ef21bf6beda730dffa8eb7ff9cabe599fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604497"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenzioni tipografiche e di scrittura del codice (Visual Basic)
Documentazione di Visual Basic utilizza seguente tipografica e convenzioni di codice.  
  
## <a name="typographic-conventions"></a>Convenzioni tipografiche  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Parole chiave specifiche della lingua e i membri di runtime hanno lettere maiuscole iniziali e vengono formattati come illustrato in questo esempio.|  
|**SmallProject**, **ButtonCollection**|Parole e frasi che viene richiesto, digitare vengono formattate come illustrato in questo esempio.|  
|[Istruzione Module](../../visual-basic/language-reference/statements/module-statement.md)|I collegamenti che è possibile fare clic per passare a un'altra pagina della Guida vengono formattati come illustrato in questo esempio.|  
|*oggetto*, *variableName*, `argumentList`|Segnaposto per le informazioni fornite vengono formattati come illustrato in questo esempio.|  
|[Ombreggiature], [ *expressionList* ]|Nella sintassi, gli elementi facoltativi sono racchiusi tra parentesi quadre.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Nella sintassi, quando è necessario effettuare una scelta tra due o più elementi, gli elementi sono racchiusi tra parentesi graffe e separati da barre verticali.<br /><br /> È necessario selezionare una sola degli elementi.|  
|[ `Protected` &#124; `Friend` ]|Nella sintassi, dopo avere la possibilità di selezionare tra due o più elementi, gli elementi sono racchiusi tra parentesi quadre e separati da barre verticali.<br /><br /> È possibile selezionare qualsiasi combinazione di elementi o nessun elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|Nella sintassi, quando è possibile selezionare non più di un elemento, ma è anche possibile omettere gli elementi completamente, gli elementi sono racchiusi tra parentesi quadre racchiuso tra parentesi graffe e separati da barre verticali.|  
|*memberName*1, *memberName*2, *memberName*3|Più istanze dello stesso segnaposto si differenzino per indici, come illustrato nell'esempio.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|Nella sintassi, i puntini di sospensione (...) viene utilizzato per indicare un numero indefinito di elementi del tipo specificato immediatamente prima i puntini di sospensione.<br /><br /> Nel codice, i puntini di sospensione indicano codice omessi per maggiore chiarezza.|  
|ESC, IMMETTERE|I nomi delle chiavi e le sequenze di tasti sulla tastiera vengono visualizzati in lettere maiuscole.|  
|ALT + F1|Quando segni più (+) vengono visualizzate tra i nomi delle chiavi, è necessario tenere premuto un tasto mentre si preme l'altro. ALT + F1 significa, ad esempio, tenere premuto il tasto ALT mentre si preme il tasto F1.|  
  
## <a name="code-conventions"></a>Convenzioni nel codice  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Esempi di codice viene visualizzato un carattere a passo fisso e formattati come illustrato in questo esempio.|  
|L'istruzione precedente imposta il valore di `sampleString` per "Hello, world!"|Gli elementi di codice del testo esplicativo vengono visualizzati in un tipo di carattere a passo fisso, come illustrato in questo esempio.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|I commenti al codice introdotte da un apostrofo (') o la parola chiave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Uno spazio seguito da un carattere di sottolineatura (_) alla fine di una riga indica che l'istruzione continua nella riga successiva.|  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per il linguaggio Visual Basic](../../visual-basic/language-reference/index.md)  
 [Parole chiave](../../visual-basic/language-reference/keywords/index.md)  
 [Membri della libreria di runtime di Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)  
 [Convenzioni di denominazione di Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Procedura: Interrompere e combinare istruzioni nel codice](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Commenti nel codice](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
