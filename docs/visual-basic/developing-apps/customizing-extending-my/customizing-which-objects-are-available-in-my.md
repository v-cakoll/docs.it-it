---
title: Personalizzazione degli oggetti disponibili in My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: bb3f8eb2e8b1cf5bce364fc4b3ce0587769bb5f9
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775206"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizzazione degli oggetti disponibili in My (Visual Basic)

In questo argomento viene descritto come controllare quali oggetti `My` sono abilitati impostando la costante di compilazione condizionale `_MYTYPE` del progetto. L'ambiente di sviluppo integrato (IDE) di Visual Studio mantiene la `_MYTYPE` costante di compilazione condizionale per un progetto sincronizzata con il tipo del progetto.  
  
## <a name="predefined-_mytype-values"></a>Valori \_MYTYPE predefiniti  

Per impostare la costante di compilazione condizionale `_MYTYPE`, è necessario usare l'opzione del compilatore `/define`. Quando si specifica un valore personalizzato per la costante `_MYTYPE`, è necessario racchiudere il valore di stringa nelle sequenze barra rovesciata/virgolette (\\"). Ad esempio, è possibile usare:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Questa tabella mostra l'impostazione della costante di compilazione condizionale `_MYTYPE` su per diversi tipi di progetto.  
  
|Tipo di progetto|\_valore MYTYPE|  
|------------------|--------------------|  
|Libreria di classi|Windows|  
|Applicazione console|Console|  
|Web|Web|  
|Libreria di controlli Web|WebControl|  
|Applicazione Windows|WindowsForms|  
|Applicazione Windows, quando si inizia con `Sub Main` personalizzati|"WindowsFormsWithCustomSubMain"|  
|Libreria di controlli Windows|Windows|  
|Servizio Windows|Console|  
|Empty|Vuoto|  
  
> [!NOTE]
> Per tutti i confronti di stringhe di compilazione condizionale viene fatta distinzione tra maiuscole e minuscole, indipendentemente dalla modalità di impostazione dell'istruzione `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Dipendenze \_costanti di compilazione  

La costante di compilazione condizionale `_MYTYPE`, a sua volta, controlla i valori di diverse altre costanti di compilazione `_MY`:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_le forme|\_MYUSERTYPE|\_WEBSERVICE|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|Console|Console|Windows|Undefined|Windows|true|  
|Personalizzato|Undefined|Undefined|Undefined|Undefined|Undefined|  
|Vuoto|Undefined|Undefined|Undefined|Undefined|Undefined|  
|Web|Undefined|Web|false|Web|false|  
|WebControl|Undefined|Web|false|Web|true|  
|"Windows" o ""|Windows|Windows|Undefined|Windows|true|  
|WindowsForms|WindowsForms|Windows|true|Windows|true|  
|"WindowsFormsWithCustomSubMain"|Console|Windows|true|Windows|true|  
  
 Per impostazione predefinita, le costanti di compilazione condizionale non definite vengono risolte in `FALSE`. È possibile specificare i valori per le costanti non definite quando si compila il progetto per eseguire l'override del comportamento predefinito.  
  
> [!NOTE]
> Quando `_MYTYPE` è impostato su "Custom", il progetto contiene lo spazio dei nomi `My`, ma non contiene oggetti. Tuttavia, l'impostazione di `_MYTYPE` su "Empty" impedisce al compilatore di aggiungere lo spazio dei nomi `My` e i relativi oggetti.  
  
 Questa tabella descrive gli effetti dei valori predefiniti delle costanti di compilazione `_MY`.  
  
|Costante|Significato|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Abilita `My.Application`, se la costante è "console," Windows "o" WindowsForms ":<br /><br /> -La versione "console" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. e dispone di un numero inferiore di membri rispetto alla versione "Windows".<br />-La versione "Windows" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>. e ha meno membri rispetto alla versione "WindowsForms".<br />-La versione "WindowsForms" di `My.Application` deriva da <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Se la costante `TARGET` è definita come "winexe", la classe include un metodo di `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Abilita `My.Computer`, se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" deriva da <xref:Microsoft.VisualBasic.Devices.ServerComputer>e ha meno membri rispetto alla versione "Windows".<br />-La versione "Windows" di `My.Computer` deriva da <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Abilita `My.Forms`, se la costante è `TRUE`.|  
|`_MYUSERTYPE`|Abilita `My.User`, se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" di `My.User` è associata all'identità utente della richiesta HTTP corrente.<br />-La versione "Windows" di `My.User` è associata all'entità corrente del thread.|  
|`_MYWEBSERVICES`|Abilita `My.WebServices`, se la costante è `TRUE`.|  
|`_MYTYPE`|Abilita `My.Log`, `My.Request`e `My.Response`, se la costante è "Web".|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
