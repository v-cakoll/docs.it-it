---
title: Personalizzazione degli oggetti disponibili in My
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: 0387aca08e3a31b0a2045369919894d88caf5b76
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330325"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizzazione degli oggetti disponibili in My (Visual Basic)

Questo argomento descrive come è possibile controllare quali `My` oggetti sono abilitati impostando la costante `_MYTYPE` di compilazione condizionale del progetto. L'ambiente di sviluppo integrato (IDE) di Visual Studio `_MYTYPE` mantiene la costante di compilazione condizionale per un progetto sincronizzato con il tipo del progetto.  
  
## <a name="predefined-_mytype-values"></a>Valori MyType \_predefiniti  

Per impostare la `_MYTYPE` costante `/define` di compilazione condizionale, è necessario usare l'opzione del compilatore. Quando si specifica un valore personalizzato per `_MYTYPE` la costante, è necessario racchiudere il valore di stringa nelle sequenze barra rovesciata/virgolette (\\"). Ad esempio, è possibile usare:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Questa tabella mostra le impostazioni `_MYTYPE` della costante di compilazione condizionale per diversi tipi di progetto.  
  
|Tipo di progetto|\_Valore MYTYPE|  
|------------------|--------------------|  
|Libreria di classi|"Windows"|  
|Applicazione console|Console|  
|Web|Web|  
|Libreria di controlli Web|WebControl|  
|Applicazione Windows|WindowsForms|  
|Applicazione Windows, quando si inizia con Custom`Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Libreria di controlli Windows|"Windows"|  
|Servizio Windows|Console|  
|Empty|Vuoto|  
  
> [!NOTE]
> Per tutti i confronti di stringhe di compilazione condizionale viene fatta distinzione tra maiuscole e minuscole, indipendentemente dalla modalità di impostazione dell' `Option Compare` istruzione.  
  
## <a name="dependent-_my-compilation-constants"></a>Costanti \_di compilazione dipendenti  

La `_MYTYPE` costante di compilazione condizionale, a sua volta, controlla i valori di `_MY` diverse altre costanti di compilazione:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_SERVIZIO Web|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|Console|Console|"Windows"|Non definito|"Windows"|TRUE|  
|Personalizzato|Non definito|Non definito|Non definito|Non definito|Non definito|  
|Vuoto|Non definito|Non definito|Non definito|Non definito|Non definito|  
|Web|Non definito|Web|FALSE|Web|FALSE|  
|WebControl|Non definito|Web|FALSE|Web|TRUE|  
|"Windows" o ""|"Windows"|"Windows"|Non definito|"Windows"|TRUE|  
|WindowsForms|WindowsForms|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|Console|"Windows"|TRUE|"Windows"|TRUE|  
  
 Per impostazione predefinita, le costanti di compilazione condizionale non definite `FALSE`vengono risolte in. È possibile specificare i valori per le costanti non definite quando si compila il progetto per eseguire l'override del comportamento predefinito.  
  
> [!NOTE]
> Quando `_MYTYPE` è impostato su "Custom", il progetto contiene lo `My` spazio dei nomi, ma non contiene oggetti. Tuttavia, l' `_MYTYPE` impostazione di su "Empty" impedisce al compilatore di `My` aggiungere lo spazio dei nomi e i relativi oggetti.  
  
 Questa tabella descrive gli effetti dei valori predefiniti delle costanti di `_MY` compilazione.  
  
|Costante|Significato|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Abilita `My.Application`se la costante è "console," Windows "o" WindowsForms ":<br /><br /> -La versione "console" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. e dispone di un numero inferiore di membri rispetto alla versione "Windows".<br />-La versione "Windows" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>. e ha meno membri rispetto alla versione "WindowsForms".<br />-La versione "WindowsForms" di `My.Application` deriva da <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Se la `TARGET` costante è definita come "winexe", la classe include un `Sub Main` metodo.|  
|`_MYCOMPUTERTYPE`|Abilita `My.Computer`se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" deriva da <xref:Microsoft.VisualBasic.Devices.ServerComputer>e ha meno membri rispetto alla versione "Windows".<br />-La versione "Windows" di `My.Computer` deriva da <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Abilita `My.Forms`se la costante è `TRUE`.|  
|`_MYUSERTYPE`|Abilita `My.User`se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" di `My.User` è associata all'identità utente della richiesta HTTP corrente.<br />-La versione "Windows" di `My.User` è associata all'entità corrente del thread.|  
|`_MYWEBSERVICES`|Abilita `My.WebServices`se la costante è `TRUE`.|  
|`_MYTYPE`|Abilita `My.Log`, `My.Request`e `My.Response`se la costante è "Web".|  
  
## <a name="see-also"></a>Vedi anche

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
