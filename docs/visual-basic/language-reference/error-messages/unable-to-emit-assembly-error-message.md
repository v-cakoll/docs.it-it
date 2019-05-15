---
title: "Impossibile creare l'assembly: <error message>"
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 012284aa42dfa29ad1a5e4ec4a4df5eaacbd4fb7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642283"
---
# <a name="unable-to-emit-assembly-error-message"></a>Impossibile creare l'assembly: \<messaggio di errore >

Il compilatore Visual Basic chiama Assembly Linker (*Al.exe*, noto anche come Alink) per generare un assembly con un manifesto e il linker segnala un errore in fase di emissione della creazione dell'assembly.

**ID errore:** BC30145

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) per spiegazioni e suggerimenti aggiuntivi.

2. Provare a firmare l'assembly manualmente, utilizzando il [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o nella [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.

### <a name="to-sign-the-assembly-manually"></a>Per firmare manualmente l'assembly

1. Usare la [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) per creare un file di coppia di chiavi pubblica/privata.

   Questo file contiene un *snk* estensione.

2. Eliminare il riferimento COM che genera l'errore dal progetto.

3. Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   In Windows 10, immettere **prompt dei comandi sviluppatore** nella casella di ricerca nella barra delle applicazioni. Quindi, selezionare **prompt dei comandi per gli sviluppatori per VS 2017** dall'elenco dei risultati.

4. Passare alla directory nella directory in cui si desidera posizionare il wrapper dell'assembly.

5. Immettere il comando seguente:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   È un esempio del comando effettivo che è possibile immettere:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Se un file o il percorso contiene spazi, utilizzare le virgolette doppie.

6. In Visual Studio, aggiungere un riferimento di Assembly .NET per il file che appena creato.

## <a name="see-also"></a>Vedere anche

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (strumento Nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Procedura: Creare una coppia di chiavi pubblica/privata](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
