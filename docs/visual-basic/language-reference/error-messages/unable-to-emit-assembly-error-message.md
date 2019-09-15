---
title: "Impossibile creare l'assembly: <error message>"
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 530aaee40be92bf72ee4b83b4141108e9b81c8a1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70968858"
---
# <a name="unable-to-emit-assembly-error-message"></a>Impossibile creare l'assembly: \<messaggio di errore >

Il compilatore Visual Basic chiama assembly linker (*al. exe*, noto anche come ALink) per generare un assembly con un manifesto e il linker segnala un errore nella fase di emissione della creazione dell'assembly.

**ID errore:** BC30145

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Esaminare il messaggio di errore tra virgolette e consultare l'argomento [al. exe](../../../framework/tools/al-exe-assembly-linker.md) per ulteriori spiegazioni e consigli.

2. Provare a firmare l'assembly manualmente, usando al [. exe](../../../framework/tools/al-exe-assembly-linker.md) o [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.

### <a name="to-sign-the-assembly-manually"></a>Per firmare manualmente l'assembly

1. Utilizzare [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)per creare un file di coppia di chiavi pubblica/privata.

   Questo file ha un'estensione *SNK* .

2. Eliminare il riferimento COM che genera l'errore dal progetto.

3. Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   In Windows 10 immettere **prompt dei comandi** per gli sviluppatori nella casella di ricerca sulla barra delle applicazioni. Selezionare quindi **prompt dei comandi per gli sviluppatori per VS 2017** dall'elenco risultati.

4. Passare alla directory in cui si vuole inserire il wrapper dell'assembly.

5. Immettere il comando seguente:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Un esempio del comando effettivo che è possibile immettere è:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Se un percorso o un file contiene spazi, utilizzare le virgolette doppie.

6. In Visual Studio aggiungere un riferimento all'assembly .NET al file appena creato.

## <a name="see-also"></a>Vedere anche

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (strumento Nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Procedura: Creare una coppia di chiavi pubblica/privata](../../../standard/assembly/create-public-private-key-pair.md)
- [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
