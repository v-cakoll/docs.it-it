---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 440e583b55765d680ee72f8574f929e335e10cdb
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590635"
---
# <a name="-bugreport"></a>-bugreport
Crea un file che è possibile usare quando si elabora un report sui bug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`file`|Obbligatorio. Il nome del file che conterrà il report sui bug. Racchiudere il nome file racchiuso tra virgolette ("") se il nome contiene uno spazio.|  
  
## <a name="remarks"></a>Note  
 Le informazioni seguenti vengono aggiunte a `file`:  
  
- Una copia di tutti i file di codice sorgente nella compilazione.  
  
- Un elenco delle opzioni del compilatore usata nella compilazione.  
  
- Informazioni sulla versione su compilatore, common language runtime e del sistema operativo.  
  
- L'eventuale output del compilatore.  
  
- Descrizione del problema per cui viene richiesto.  
  
- Una descrizione del modo in cui si può risolvere il problema dovrebbe essere risolto, per cui viene richiesto.  
  
 Poiché una copia di tutti i file di codice sorgente è incluso `file`, è possibile riprodurre l'errore del codice (sospetti) nel programma più breve possibile.  
  
> [!IMPORTANT]
>  Il `-bugreport` opzione produce un file che contiene informazioni potenzialmente riservate. Ciò include l'ora corrente, versione del compilatore, versione di .NET Framework, versione del sistema operativo, nome utente, gli argomenti della riga di comando con cui il compilatore è stato eseguito, tutto il codice sorgente e il formato binario di qualsiasi assembly di riferimento. Questa opzione è possibile accedere specificando le opzioni della riga di comando nel file Web. config per una compilazione di un'applicazione ASP.NET sul lato server. Per evitare questo problema, modificare il file Machine. config per impedire agli utenti di compilazione sul server.  
  
 Se questa opzione viene usata con `-errorreport:prompt`, `-errorreport:queue`, o `-errorreport:send`, e l'applicazione rileva un errore interno del compilatore, le informazioni contenute in `file` verranno inviate a Microsoft Corporation. Tali informazioni consentono i tecnici Microsoft di identificare la causa dell'errore e potrebbero contribuire a migliorare la prossima versione di Visual Basic. Per impostazione predefinita, nessuna informazione viene inviata a Microsoft. Tuttavia, quando si compila un'applicazione usando `-errorreport:queue`, che è abilitato per impostazione predefinita, l'applicazione raccoglie le segnalazioni degli errori. Quindi, quando l'amministratore del computer si connette, il sistema di segnalazione errori consente di visualizzare una finestra popup che consente all'amministratore di inoltrare a Microsoft i report degli errori che si sono verificati dopo l'accesso.  
  
> [!NOTE]
>  Il `/bugreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo quando esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente viene compilato `T2.vb` e tutte le informazioni di segnalazione di errori nel file `Problem.txt`.  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Elemento trustLevel per securityPolicy (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
