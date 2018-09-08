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
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082057"
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
|`+` &#124; `-`|Facoltativo. Specifica di +, o semplicemente `-doc`, indica al compilatore di generare le informazioni sulla documentazione e inserirlo in un file XML. Che specifica `-` equivale a non specificare `-doc`, non causando Nessuna informazione sulla documentazione da creare.|  
|`file`|Richiesto se è usato `-doc:`. Specifica il file XML di output, che viene popolato con i commenti dai file di codice sorgente della compilazione. Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette doppie ("").|  
  
## <a name="remarks"></a>Note  
 Il `-doc` opzione consente di controllare se il compilatore genera un file XML contenente i commenti della documentazione. Se si usa la `-doc:file` informazioni sulla sintassi, il `file` parametro specifica il nome del file XML. Se si usa `-doc` o `-doc+`, il compilatore prende il nome del file XML dal file eseguibile o libreria che il compilatore sta creando. Se si usa `-doc-` o non si specifica il `-doc` opzione, il compilatore non crea un file XML.  
  
 Nei file di codice sorgente, i commenti della documentazione possono precedere le definizioni seguenti:  
  
-   Definito dall'utente tipi, ad esempio un [classe](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaccia](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   I membri, ad esempio un campo [evento](../../../visual-basic/language-reference/statements/event-statement.md), [proprietà](../../../visual-basic/language-reference/statements/property-statement.md), [funzione](../../../visual-basic/language-reference/statements/function-statement.md), oppure [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Usare il file XML generato con Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) funzionalità, si supponga che il nome del file del file XML sia lo stesso dell'assembly a cui si vuole supportare. Assicurarsi che il file XML è nella stessa directory dell'assembly in modo che sia possibile anche quando l'assembly viene fatto riferimento nel progetto di Visual Studio, il file con estensione XML. File di documentazione XML non sono necessari per funzionare per il codice all'interno di un progetto o all'interno dei progetti cui viene fatto riferimento da un progetto di IntelliSense.  
  
 A meno che non si esegue la compilazione con `/target:module`, il file XML contiene i tag `<assembly></assembly>`. Questi tag specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.  
  
 Visualizzare [tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md) per modi per generare la documentazione dai commenti nel codice.  
  
|Per impostare - doc in Visual Studio ambiente di sviluppo integrato|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Impostare il valore nel **file di documentazione XML genera** casella.|  
  
## <a name="example"></a>Esempio  
 Visualizzare [documentare il codice con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) per un esempio.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
