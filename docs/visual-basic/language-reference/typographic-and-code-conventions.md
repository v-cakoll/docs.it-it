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
ms.openlocfilehash: 3255dff8268cd5500a1244716f37bf30f5b43cfb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828628"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenzioni tipografiche e di scrittura del codice (Visual Basic)
Documentazione di Visual Basic Usa la seguente tipografici e convenzioni di codice.  
  
## <a name="typographic-conventions"></a>Convenzioni tipografiche  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Le parole chiave specifiche del linguaggio e i membri di runtime sono lettere maiuscole iniziali e sono formattati come illustrato in questo esempio.|  
|**SmallProject**, **ButtonCollection**|Parole e frasi che viene richiesto al tipo vengono formattate come illustrato in questo esempio.|  
|[Istruzione Module](../../visual-basic/language-reference/statements/module-statement.md)|I collegamenti che è possibile fare clic per passare a un'altra pagina della Guida sono formattati come illustrato in questo esempio.|  
|*object*, *variableName*, `argumentList`|Segnaposto per le informazioni fornite sono formattati come illustrato in questo esempio.|  
|[Ombreggiature], [ *expressionList* ]|Nella sintassi, gli elementi facoltativi vengono racchiusi tra parentesi quadre.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|Nella sintassi, quando è necessario effettuare una scelta tra due o più elementi, gli elementi sono racchiusi tra parentesi e separati da barre verticali.<br /><br /> È necessario selezionare uno e uno solo, degli elementi.|  
|[ `Protected` &#124; `Friend` ]|Nella sintassi, quando si hanno la possibilità di selezionare tra due o più elementi, gli elementi sono racchiusi tra parentesi quadre e separati da barre verticali.<br /><br /> È possibile selezionare qualsiasi combinazione degli elementi o nessun elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|Nella sintassi, quando è possibile selezionare non più di un elemento, ma è anche possibile omettere gli elementi completamente, gli elementi racchiusi tra parentesi quadre racchiuse tra parentesi graffe e separati da barre verticali.|  
|*nomeMembro*1, *memberName*2, *memberName*3|Più istanze dello stesso segnaposto si differenziano per gli indici, come illustrato nell'esempio.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|Nella sintassi, i puntini di sospensione (...) viene utilizzato per indicare un numero indefinito di elementi del tipo specificato immediatamente prima dei puntini di sospensione.<br /><br /> Nel codice, i puntini di sospensione indicano codice omessa per chiarezza.|  
|ESC, IMMETTERE|I nomi delle chiavi e le sequenze di tasti sulla tastiera vengono visualizzati in lettere maiuscole.|  
|ALT + F1|Quando vengono visualizzati segni più (+) tra i nomi delle chiavi, è necessario tenere premuto un tasto mentre vengono premuti l'altro. ALT + F1 significa, ad esempio, tenere premuto il tasto ALT mentre si preme il tasto F1.|  
  
## <a name="code-conventions"></a>Convenzioni del codice  
  
|Esempio|Descrizione|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Esempi di codice vengono visualizzati in un tipo di carattere a passo fisso e sono formattati come illustrato in questo esempio.|  
|L'istruzione precedente imposta il valore di `sampleString` a "Hello, world!"|Gli elementi di codice in un testo descrittivo visualizzato in un tipo di carattere a passo fisso, come illustrato in questo esempio.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|I commenti al codice introdotte da un apostrofo (') o la parola chiave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Uno spazio seguito da un carattere di sottolineatura (_) alla fine di una riga indica che l'istruzione di proseguire la riga seguente.|  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio Visual Basic](../../visual-basic/language-reference/index.md)
- [Parole chiave](../../visual-basic/language-reference/keywords/index.md)
- [Membri della libreria di runtime di Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)
- [Convenzioni di denominazione di Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Commenti nel codice](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
