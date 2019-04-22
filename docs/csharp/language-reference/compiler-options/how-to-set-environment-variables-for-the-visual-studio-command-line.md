---
title: 'Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio'
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 9eea7f76d386816aad060e9b99cea6b906a09ab9
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612121"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio

Il file VsDevCmd.bat imposta le variabili di ambiente appropriate per abilitare le compilazioni da riga di comando.

> [!NOTE]
> Il file VsDevCmd.bat è un nuovo file fornito con Visual Studio 2017. Visual Studio 2015 e versioni precedenti usano VSVARS32.bat per gli stessi scopi. Il file era archiviato in \Programmi\Microsoft Visual Studio\\*Versione*\Common7\Tools o Programmi (x86)\Microsoft Visual Studio\\*Versione*\Common7\Tools.

Se la versione corrente di Visual Studio è installata in un computer che include anche la versione precedente di Visual Studio, non eseguire VsDevCmd.bat e VSVARS32.BAT da diverse versioni nella stessa finestra del prompt dei comandi. È invece necessario eseguire il comando per ogni versione in una finestra specifica.

### <a name="to-run-vsdevcmdbat"></a>Per eseguire VsDevCmd.BAT

1. Dal menu **Start** aprire il **Prompt dei comandi per gli sviluppatori per VS 2017**.  È disponibile nella cartella **Visual Studio 2017**.

2. Passare alla sottodirectory di installazione \Programmi\Microsoft Visual Studio\\*Versione*\\*Offerta*\Common7\Tools o \Programmi (x86)\Microsoft Visual Studio\\*Versione*\\*Offerta*\Common7\Tools.  (*Versione* è *2017* per la versione corrente. *Offerta* è *Enterprise*, *Professional* o *Community*.)

3. Eseguire VsDevCmd.bat digitando **VsDevCmd**.

    > [!CAUTION]
    > Il file VsDevCmd.bat può variare da computer a computer. Non sostituire un file VsDevCmd.bat mancante o danneggiato con un file VsDevCmd.bat da un altro computer. Rieseguire invece l'installazione per sostituire il file mancante.

### <a name="available-options-for-vsdevcmdbat"></a>Opzioni disponibili per VsDevCmd.BAT

Per visualizzare le opzioni disponibili per VsDevCmd.BAT, eseguire il comando con l'opzione `-help`:

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>Vedere anche

- [Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
