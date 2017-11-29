---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7090142f940ae42f554fc0ba16bcc80d8537e38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bugreport"></a>/bugreport
Crea un file che è possibile utilizzare quando si invia una segnalazione bug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`file`|Obbligatorio. Il nome del file che conterrà il report sui bug. Racchiudere il nome del file tra virgolette ("") se il nome contiene uno spazio.|  
  
## <a name="remarks"></a>Note  
 Le informazioni seguenti vengono aggiunte a `file`:  
  
-   Una copia di tutti i file di codice sorgente nella compilazione.  
  
-   Un elenco di opzioni del compilatore utilizzate nella compilazione.  
  
-   Informazioni sulla versione relative del compilatore, common language runtime e del sistema operativo.  
  
-   L'eventuale output del compilatore.  
  
-   Descrizione del problema, per cui viene richiesto.  
  
-   Una descrizione di come si ritiene che il problema deve essere corretto per il quale viene richiesto.  
  
 Poiché una copia di tutti i file di codice sorgente è incluso `file`, è possibile riprodurre l'errore del codice (sospetta) nel programma più breve possibile.  
  
> [!IMPORTANT]
>  Il `/bugreport` opzione produce un file che contiene informazioni potenzialmente riservate. Ora corrente, la versione del compilatore, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] versione, versione del sistema operativo, nome utente, gli argomenti della riga di comando con cui è stato eseguito il compilatore, tutto il codice sorgente e il formato binario di qualsiasi assembly a cui viene fatto riferimento. Questa opzione è possibile accedere mediante le opzioni della riga di comando nel file Web. config per una compilazione sul lato server di un [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] dell'applicazione. Per evitare questo problema, modificare il file Machine. config per impedire agli utenti di compilazione sul server.  
  
 Se questa opzione viene utilizzata con `/errorreport:prompt`, `/errorreport:queue`, o `/errorreport:send`, e nell'applicazione viene rilevato un errore interno del compilatore, le informazioni contenute in `file` viene inviato a Microsoft Corporation. Tali informazioni consentiranno tecnici Microsoft di identificare la causa dell'errore e potrebbe contribuire a migliorare la versione successiva di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Per impostazione predefinita, nessuna informazione viene inviata a Microsoft. Tuttavia, quando si compila un'applicazione utilizzando `/errorreport:queue`, cui è abilitata per impostazione predefinita, l'applicazione recupera i report degli errori. Quindi, quando l'amministratore del computer si connette, il sistema di segnalazione errori consente di visualizzare una finestra popup che consente all'amministratore di inoltrare a Microsoft i report degli errori che si sono verificati dopo l'accesso.  
  
> [!NOTE]
>  Il `/bugreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo quando esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene compilata `T2.vb` e tutte le informazioni di segnalazione nel file `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Elemento di trustLevel per securityPolicy (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
