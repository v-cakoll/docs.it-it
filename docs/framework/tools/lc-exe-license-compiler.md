---
title: Lc.exe (Compilatore licenze)
description: Utilizzare Lc.exe, il compilatore delle licenze. Questo strumento legge i file di testo che contengono informazioni sulla licenza e crea un file binario da incorporare in un eseguibile CLR come risorsa.
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 45a80ba7c3e24c0f419758315b2d2daafd3890f4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164248"
---
# <a name="lcexe-license-compiler"></a>Lc.exe (Compilatore licenze)
Il Compilatore licenze legge file di testo contenenti informazioni sulla licenza e produce un file binario che è possibile incorporare come risorsa in un eseguibile di Common Language Runtime.  
  
 Un file LICX viene generato o aggiornato automaticamente mediante Progettazione Windows Form ogni volta che un controllo concesso in licenza viene aggiunto al form. Durante la compilazione, il file di testo LICX viene convertito in una risorsa binaria con estensione licenses che fornisce il supporto per la gestione delle licenze dei controlli .NET. La risorsa binaria verrà quindi incorporata nell'output del progetto.  
  
 La compilazione incrociata fra 32 bit e 64 bit non è supportata quando si usa il Compilatore licenze nel corso della compilazione del progetto. Questo avviene perché il Compilatore licenze deve caricare assembly e non è consentito caricare assembly a 64 bit da un'applicazione a 32 bit e viceversa. In questo caso, usare il Compilatore licenze dalla riga di comando per compilare manualmente la licenza e specificare l'architettura corrispondente.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/complist:** *filename*|Specifica il nome di un file contenente l'elenco dei componenti provvisti di licenza da includere nel file LICENSES. A ciascun componente viene fatto riferimento mediante il nome completo, specificando un solo componente per riga.<br /><br /> Se si usa la riga di comando sarà possibile specificare un file separato per ciascun form del progetto. Lc.exe accetta più file di input e produce un unico file LICENSES.|  
|**/h**[**ELP**]|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/i:** *modulo*|Specifica i moduli contenenti i componenti elencati nel file **/complist**. Per specificare più moduli, usare più flag **/i**.|  
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|  
|**/outDir:** *percorso*|Specifica la directory in cui inserire il file LICENSES di output.|  
|**/target:** *targetPE*|Specifica l'eseguibile per cui viene generato il file LICENSES.|  
|**/v**|Specifica la modalità dettagliata. Visualizza le informazioni sullo stato della compilazione.|  
|**@***file*|Specifica il file di risposta (.rsp).|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="example"></a>Esempio  
  
1. Se si usa un controllo con licenza `MyCompany.Samples.LicControl1` contenuto in `Samples.DLL` all'interno di un'applicazione denominata `HostApp.exe`*,* è possibile creare il file `HostAppLic.txt` includendo gli elementi seguenti.  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. Creare il file LICENSES denominato `HostApp.exe.licenses` usando il comando che segue.  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. Compilare `HostApp.exe` includendo il file LICENSES come risorsa. Se l'applicazione fosse in C#, si utilizzerebbe il seguente comando per compilarla:  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 Il comando che segue compila `myApp.licenses` sulla base degli elenchi di componenti provvisti di licenza specificati da `hostapplic.txt`, `hostapplic2.txt` e `hostapplic3.txt`. L'argomento `modulesList` specifica i moduli contenenti i componenti provvisti di licenza.  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a>Esempio di file di risposta  
 Nell'elenco seguente è riportato un esempio di file di risposta, `response.rsp`. Per altre informazioni sui file di risposta, vedere [File di risposta](/visualstudio/msbuild/msbuild-response-files).  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 La riga di comando seguente usa il file `response.rsp`.  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Al.exe (assembly linker)](al-exe-assembly-linker.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
