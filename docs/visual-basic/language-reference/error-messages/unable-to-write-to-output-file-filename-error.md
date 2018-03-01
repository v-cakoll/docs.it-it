---
title: 'Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d142a8c741a9f0e25b8ac3c0002d04f437bf0ca9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;
Si è verificato un problema durante la creazione del file.  
  
 Non è possibile aprire un file di output per la scrittura. È possibile che il file (o la cartella contenente il file) sia aperto per l'uso esclusivo da parte di un altro processo o è stato impostato l'attributo di sola lettura del file.  
  
 Di seguito sono elencate alcune situazioni comuni in cui un file è aperto in modo esclusivo:  
  
-   L'applicazione è già in esecuzione e sta usando i file correlati. Per risolvere il problema, assicurarsi che l'applicazione non sia in esecuzione.  
  
-   Un'altra applicazione ha aperto il file. Per risolvere il problema, assicurarsi che altre applicazioni non accedano ai file. Non è sempre semplice capire quale applicazione sta accedendo ai file. In questo caso, riavviare il computer potrebbe rappresentare il modo più semplice per arrestare l'applicazione.  
  
 Se anche uno solo dei file di output del progetto è contrassegnato come di sola lettura, sarà generata questa eccezione.  
  
 **ID errore:** BC31019  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Ripetere la compilazione del programma, per controllare se l'errore si verifica di nuovo.  
  
2.  Se l'errore si ripresenta, salvare il lavoro e riavviare [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].  
  
3.  Se l'errore si ripresenta, riavviare il computer.  
  
4.  Se l'errore si ripete, reinstallare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
5.  Se l'errore persiste dopo la reinstallazione, inviare una notifica al Servizio Supporto Tecnico Clienti Microsoft.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>Per controllare gli attributi di file in Esplora file  
  
1.  Aprire la cartella a cui si è interessati.  
  
2.  Fare clic su di **viste** icona e scegliere **dettagli**.  
  
3.  Fare doppio clic sull'intestazione di colonna e scegliere **attributi** dall'elenco a discesa.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>Per modificare gli attributi di un file o una cartella  
  
1.  In **Esplora File**, fare doppio clic su file o della cartella e scegliere **proprietà**.  
  
2.  Nel **attributi** sezione del **generale** scheda, deseleziona il **Read-only** casella.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>Vedere anche  
 [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
