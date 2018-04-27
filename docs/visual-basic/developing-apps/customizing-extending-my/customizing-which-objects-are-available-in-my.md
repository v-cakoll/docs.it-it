---
title: Personalizzazione degli oggetti disponibili in My (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 669641a2b6ecbf988f6cad68acf52c5561b32515
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizzazione degli oggetti disponibili in My (Visual Basic)
Questo argomento viene descritto come è possibile controllare quali `My` gli oggetti sono abilitati tramite l'impostazione del progetto `_MYTYPE` costante di compilazione condizionale. IDE di Visual Studio Integrated Development ambiente () consente di mantenere il `_MYTYPE` costante di compilazione condizionale per un progetto sincronizzata con il tipo di progetto.  
  
## <a name="predefined-mytype-values"></a>Valori predefiniti di MyType  
 È necessario utilizzare il `/define` per impostare l'opzione del compilatore di `_MYTYPE` costante di compilazione condizionale. Quando si specifica il valore per il `_MYTYPE` costante, è necessario racchiudere il valore stringa in una barra rovesciata/virgolette (\\") le sequenze. Ad esempio, è possibile utilizzare:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Questa tabella vengono mostrate le operazioni di `_MYTYPE` viene impostata la costante di compilazione condizionale per diversi tipi di progetto.  
  
|Tipo di progetto|Valore di MyType|  
|------------------|--------------------|  
|Libreria di classi|"Windows"|  
|Applicazione console|"Console"|  
|Web|"Web".|  
|Libreria di controlli Web|"WebControl"|  
|Applicazione Windows|"WindowsForms"|  
|Applicazione di Windows, quando si avvia con personalizzato `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Libreria di controlli Windows|"Windows"|  
|Servizio Windows|"Console"|  
|Empty|"Vuoto"|  
  
> [!NOTE]
>  Tutti i confronti di stringa di compilazione condizionale tra maiuscole e minuscole, indipendentemente dal modo in cui il `Option Compare` istruzione è impostata.  
  
## <a name="dependent-my-compilation-constants"></a>Costanti di compilazione dipendenti My  
 Il `_MYTYPE` costante di compilazione condizionale, controlla a sua volta, i valori degli altri `_MY` costanti di compilazione:  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Undefined|"Windows"|true|  
|"Custom"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Vuoto"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Web".|Undefined|"Web".|false|"Web".|false|  
|"WebControl"|Undefined|"Web".|false|"Web".|true|  
|"Windows" o ""|"Windows"|"Windows"|Undefined|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|true|"Windows"|true|  
  
 Per impostazione predefinita, le costanti di compilazione condizionale non definite risolte in `FALSE`. Quando si compila il progetto per eseguire l'override del comportamento predefinito, è possibile specificare valori per le costanti non definite.  
  
> [!NOTE]
>  Quando `_MYTYPE` è impostato su "Custom", il progetto contiene il `My` dello spazio dei nomi, ma non contiene oggetti. Tuttavia, l'impostazione `_MYTYPE` per "Vuoto" impedisce al compilatore di aggiungere il `My` dello spazio dei nomi e i relativi oggetti.  
  
 Questa tabella vengono descritti gli effetti dei valori predefiniti del `_MY` costanti di compilazione.  
  
|Costante|Significato|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Abilita `My.Application`, se la costante è "Finestre della Console,", "o"WindowsForms":<br /><br /> -La versione "Console" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. e include meno membri rispetto alla versione "Windows".<br />-La versione "Windows" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>e include meno membri rispetto alla versione "WindowsForms".<br />-La versione "WindowsForms" di `My.Application` deriva da <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Se il `TARGET` costante è definita come "winexe", quindi la classe include un `Sub Main` metodo.|  
|`_MYCOMPUTERTYPE`|Abilita `My.Computer`, se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" deriva da <xref:Microsoft.VisualBasic.Devices.ServerComputer>, e include meno membri rispetto alla versione "Windows".<br />-La versione "Windows" `My.Computer` deriva da <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Abilita `My.Forms`, se la costante è `TRUE`.|  
|`_MYUSERTYPE`|Abilita `My.User`, se la costante è "Web" o "Windows":<br /><br /> -La versione "Web" `My.User` associata con l'identità dell'utente della richiesta HTTP corrente.<br />-La versione "Windows" `My.User` è associata l'entità del thread corrente.|  
|`_MYWEBSERVICES`|Abilita `My.WebServices`, se la costante è `TRUE`.|  
|`_MYTYPE`|Abilita `My.Log`, `My.Request`, e `My.Response`, se la costante è "Web".|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
