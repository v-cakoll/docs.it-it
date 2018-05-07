---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b64372d4b6063da85739e939bb33abd4650ecb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-doc"></a>-doc
Elabora commenti sulla documentazione in un file XML.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Specificando +, o semplicemente `-doc`, indica al compilatore di generare informazioni relative alla documentazione e inserirle in un file XML. Specifica di `-` è l'equivalente della specifica di non `-doc`, non causando alcuna informazione di documentazione da creare.|  
|`file`|Richiesto se è usato `-doc:`. Specifica il file XML di output, che viene popolato con i commenti dai file di codice sorgente della compilazione. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").|  
  
## <a name="remarks"></a>Note  
 Il `-doc` opzione controlli se il compilatore genera un file XML contenente i commenti della documentazione. Se si utilizza il `-doc:file` sintassi, il `file` parametro specifica il nome del file XML. Se si utilizza `-doc` o `-doc+`, il compilatore prende il nome del file XML dal file eseguibile o libreria che il compilatore sta creando. Se si utilizza `-doc-` o non si specifica il `-doc` opzione, il compilatore non crea un file XML.  
  
 Nei file di codice sorgente, i commenti della documentazione possono precedere le definizioni seguenti:  
  
-   Definite dall'utente tipi, ad esempio un [classe](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaccia](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   I membri, ad esempio un campo, [evento](../../../visual-basic/language-reference/statements/event-statement.md), [proprietà](../../../visual-basic/language-reference/statements/property-statement.md), [funzione](../../../visual-basic/language-reference/statements/function-statement.md), o [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Per utilizzare il file XML generato con Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) funzionalità, si supponga che il nome del file del file XML sia da quella dell'assembly a cui si desidera supportare. Verificare che il file XML è nella stessa directory dell'assembly in modo che sia possibile anche quando l'assembly viene fatto riferimento nel progetto di Visual Studio, il file con estensione XML. File di documentazione XML non sono necessari per IntelliSense funzioni per il codice all'interno di un progetto o all'interno dei progetti a cui fa riferimento un progetto.  
  
 A meno che non esegue la compilazione con `/target:module`, il file XML contiene il tag `<assembly></assembly>`. Questi tag specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.  
  
 Vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) per informazioni sulla generazione di documentazione dai commenti nel codice.  
  
|Per impostare - ambiente di sviluppo integrato di documenti in Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Impostare il valore di **file di documentazione XML generare** casella.|  
  
## <a name="example"></a>Esempio  
 Vedere [documentare il codice con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) per un esempio.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
