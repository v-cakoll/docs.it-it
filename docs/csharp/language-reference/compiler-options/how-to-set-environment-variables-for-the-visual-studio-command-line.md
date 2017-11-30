---
title: 'Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio'
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Procedura: Impostare le variabili di ambiente per la riga di comando di Visual Studio

Il file VsDevCmd.bat imposta le variabili di ambiente appropriate per abilitare le compilazioni da riga di comando. Per ulteriori informazioni su VsDevCmd.bat, vedere [della Knowledge Base Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  

> [!NOTE]
> Il file VsDevCmd.bat è un nuovo file fornito con Visual Studio 2017. Visual Studio 2015 e versioni precedenti utilizzato VSVARS32.bat allo stesso scopo. Questo file è stato archiviato in \Programmi\Microsoft Visual Studio\\*versione*\Common7\Tools o programmi (x86) \Microsoft Visual Studio\\*versione*\Common7\Tools.
  
Se la versione corrente di Visual Studio è installata in un computer che dispone anche di una versione precedente di Visual Studio, è necessario eseguire non VsDevCmd.bat e VSVARS32. BAT da diverse versioni nella stessa finestra del prompt dei comandi. In alternativa, è necessario eseguire il comando per ogni versione nella propria finestra.
  
### <a name="to-run-vsdevcmdbat"></a>Per eseguire VsDevCmd.BAT  
  
1.  Dal **avviare** menu, aprire il **prompt dei comandi per sviluppatori per Visual Studio 2017**.  È il **Visual Studio 2017** cartella.
  
2.  Modificare in \Programmi\Microsoft Visual Studio\\*versione*\\*offerta*\Common7\Tools o \Programmi file (x86) \Microsoft Visual Studio\\ *Versione*\\*offerta*\Common7\Tools sottodirectory dell'installazione.  (*Versione* è *2017* per la versione corrente. *Offerta* è uno dei *Enterprise*, *Professional* o *Community*.)
  
3.  Eseguire VsDevCmd.bat digitando **VsDevCmd**.  
  
    > [!CAUTION]
    >  VsDevCmd.bat può variare da computer a computer. Non sostituire un file VsDevCmd.bat mancante o danneggiato con un VsDevCmd.bat da un altro computer. Rieseguire invece l'installazione per sostituire il file mancante.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione dalla riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
