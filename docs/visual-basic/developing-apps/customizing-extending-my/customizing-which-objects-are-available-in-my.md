---
title: Personalizzazione degli oggetti disponibili in My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: c0b47521c6a62071466ae4193cd8553bdfb3dcde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890371"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Personalizzazione degli oggetti disponibili in My (Visual Basic)

In questo argomento viene descritto come è possibile controllare quali `My` gli oggetti vengono abilitati mediante l'impostazione del progetto `_MYTYPE` costante di compilazione condizionale. Mantiene la Visual Studio integrata sviluppo ambiente (IDE) di `_MYTYPE` costante di compilazione condizionale per un progetto sincronizzata con il tipo di progetto.  
  
## <a name="predefined-mytype-values"></a>Predefined \_MYTYPE valori  

È necessario usare il `/define` opzione del compilatore per impostare il `_MYTYPE` costante di compilazione condizionale. Quando si specifica un valore personalizzato per il `_MYTYPE` costante, è necessario racchiudere il valore della stringa nella barra rovesciata/virgolette (\\") le sequenze. Ad esempio, è possibile usare:  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 La tabella seguente mostra cosa la `_MYTYPE` viene impostata la costante di compilazione condizionale per diversi tipi di progetto.  
  
|Tipo di progetto|\_Valore MYTYPE|  
|------------------|--------------------|  
|Libreria di classi|"Windows"|  
|Applicazione console|"Console"|  
|Web|"Web"|  
|Libreria di controlli Web|"WebControl"|  
|Applicazione Windows|"WindowsForms"|  
|Applicazione di Windows, quando si avvia con personalizzato `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Libreria di controlli Windows|"Windows"|  
|Servizio Windows|"Console"|  
|Empty|"Vuoto"|  
  
> [!NOTE]
> Tutti i confronti di stringhe di compilazione condizionale sono tra maiuscole e minuscole, indipendentemente dal modo in cui il `Option Compare` istruzione è impostata.  
  
## <a name="dependent-my-compilation-constants"></a>Dipendenti \_MY costanti di compilazione  

Il `_MYTYPE` costante di compilazione condizionale, determina a sua volta, i valori degli altri `_MY` costanti di compilazione:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Undefined|"Windows"|TRUE|  
|"Custom"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Vuoto"|Undefined|Undefined|Undefined|Undefined|Undefined|  
|"Web"|Undefined|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|Undefined|"Web"|FALSE|"Web"|TRUE|  
|"Windows" o ""|"Windows"|"Windows"|Undefined|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 Per impostazione predefinita, le costanti di compilazione condizionale non definite risolte in `FALSE`. Quando si compila il progetto per eseguire l'override del comportamento predefinito, è possibile specificare i valori per le costanti non definite.  
  
> [!NOTE]
> Quando `_MYTYPE` è impostata su "Custom", il progetto contiene il `My` dello spazio dei nomi, ma non contiene alcun oggetto. Tuttavia, impostando `_MYTYPE` per "Vuoto" impedisce al compilatore di aggiungere il `My` dello spazio dei nomi e i relativi oggetti.  
  
 La tabella seguente descrive gli effetti dei valori predefiniti del `_MY` costanti di compilazione.  
  
|Costante|Significato|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Abilita `My.Application`, se la costante è "Console", Windows, "o"Windows Form":<br /><br /> -La versione "Console" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>. e include meno membri rispetto alla versione "Windows".<br />-La versione "Windows" deriva da <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>e include meno membri rispetto alla versione di "Windows Form".<br />-La versione di "Windows Form" del `My.Application` deriva da <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Se il `TARGET` costante viene definita come "winexe", quindi la classe include una `Sub Main` (metodo).|  
|`_MYCOMPUTERTYPE`|Abilita `My.Computer`, se la costante è "Web" o "Windows":<br /><br /> -La versione di "Web" deriva da <xref:Microsoft.VisualBasic.Devices.ServerComputer>, e include meno membri rispetto alla versione "Windows".<br />-La versione "Windows" del `My.Computer` deriva da <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Abilita `My.Forms`, se la costante è `TRUE`.|  
|`_MYUSERTYPE`|Abilita `My.User`, se la costante è "Web" o "Windows":<br /><br /> -La versione di "Web" di `My.User` associato con l'identità dell'utente della richiesta HTTP corrente.<br />-La versione "Windows" di `My.User` associato con l'oggetto principal del thread corrente.|  
|`_MYWEBSERVICES`|Abilita `My.WebServices`, se la costante è `TRUE`.|  
|`_MYTYPE`|Abilita `My.Log`, `My.Request`, e `My.Response`, se la costante è "Web".|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
- [Oggetto My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
