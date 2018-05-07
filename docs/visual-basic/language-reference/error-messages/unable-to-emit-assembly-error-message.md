---
title: "Impossibile creare l'assembly: &lt;messaggio di errore&gt;"
ms.date: 07/20/2015
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 8f497069088ad30a3be58d02caa0a32f7f1b21b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Impossibile creare l'assembly: &lt;messaggio di errore&gt;
Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto e il linker segnala un errore in fase di emissione della creazione dell'assembly.  
  
 **ID errore:** BC30145  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Per spiegazioni e suggerimenti aggiuntivi.  
  
2.  Tenta di firmare l'assembly manualmente, utilizzando il [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
3.  Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>Per firmare manualmente l'assembly  
  
1.  Usare il [Sn.exe (strumento nome sicuro)][Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)) per creare un file di coppia di chiavi pubblica/privata.  
  
     L'estensione di questo file è .snk.  
  
2.  Eliminare il riferimento COM che genera l'errore dal progetto.  
  
3.  Da Windows **avviare** dal menu **programmi**, scegliere **Microsoft Visual Studio 2008**, scegliere **Visual Studio Tools**, e quindi fare clic su **Prompt dei comandi di Visual Studio 2008**.  
  
4.  Passare alla directory in cui si desidera posizionare il wrapper dell'assembly.  
  
5.  Digitare il codice seguente.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Il codice da digitare potrebbe essere simile al seguente.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Se contiene spazi, il file o il percorso deve essere racchiuso tra virgolette doppie (").  
  
6.  In Visual Studio, aggiungere un riferimento Assembly .NET al file che appena creato.  
  
## <a name="see-also"></a>Vedere anche  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sn.exe (strumento nome sicuro)] [Sn.exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Procedura: Creare una coppia di chiavi pubblica/privata](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
