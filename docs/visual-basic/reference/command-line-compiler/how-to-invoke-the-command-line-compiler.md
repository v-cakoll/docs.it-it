---
title: 'Procedura: richiamare il compilatore da riga di comando'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344265"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Procedura: richiamare il compilatore da riga di comando (Visual Basic)

È possibile richiamare il compilatore da riga di comando digitando il nome del relativo file eseguibile nella riga di comando, noto anche come prompt di MS-DOS. Se si esegue la compilazione dal prompt dei comandi di Windows predefinito, è necessario digitare il percorso completo del file eseguibile. Per eseguire l'override di questo comportamento predefinito, è possibile usare la Prompt dei comandi per gli sviluppatori per Visual Studio o modificare la variabile di ambiente PATH. Entrambi consentono di compilare da qualsiasi directory semplicemente digitando il nome del compilatore.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Per richiamare il compilatore usando il Prompt dei comandi per gli sviluppatori per Visual Studio

1. Aprire la cartella del programma Strumenti di Visual Studio nel gruppo Microsoft Visual Studio Program.

2. È possibile usare la Prompt dei comandi per gli sviluppatori per Visual Studio per accedere al compilatore da qualsiasi directory nel computer, se è installato Visual Studio.

3. Richiamare il Prompt dei comandi per gli sviluppatori per Visual Studio.

4. Nella riga di comando digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.

    Ad esempio, se il codice sorgente è stato archiviato in una directory `SourceFiles`denominata, si aprirà il prompt dei comandi `cd SourceFiles` e il tipo per passare a tale directory. Se la directory contiene un file di origine `Source.vb`denominato, è possibile compilarlo `vbc.exe Source.vb`digitando.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Per impostare la variabile di ambiente PATH sul compilatore per il prompt dei comandi di Windows

1. Utilizzare la funzionalità di ricerca di Windows per trovare vbc. exe nel disco locale.

    Il nome esatto della directory in cui si trova il compilatore dipende dalla posizione della directory di Windows e dalla versione di ".NET Framework" installata. Se è installata più di una versione di ".NET Framework", è necessario determinare la versione da usare (in genere la versione più recente).

2. Dal menu **Start** , fare clic con il pulsante destro del mouse su **computer locale**, quindi scegliere **proprietà** dal menu di scelta rapida.

3. Fare clic sulla scheda **Avanzate** e quindi su **Variabili di ambiente**.

4. Nel riquadro variabili di **sistema** selezionare **percorso** dall'elenco e fare clic su **modifica**.

5. Nella finestra di dialogo Modifica variabile di **sistema** spostare il punto di inserimento alla fine della stringa nel campo **valore variabile** e digitare un punto e virgola (;) seguito dal nome completo della directory disponibile nel passaggio 1.

6. Fare clic su **OK** per confermare le modifiche e chiudere le finestre di dialogo.

     Dopo aver modificato la variabile di ambiente PATH, è possibile eseguire il compilatore Visual Basic al prompt dei comandi di Windows da qualsiasi directory del computer.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Per richiamare il compilatore tramite il prompt dei comandi di Windows

1. Dal menu **Start** fare clic sulla cartella **Accessories** , quindi aprire il prompt dei **comandi di Windows**.

2. Nella riga di comando digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.

     Ad esempio, se il codice sorgente è stato archiviato in una directory `SourceFiles`denominata, si aprirà il prompt dei comandi `cd SourceFiles` e il tipo per passare a tale directory. Se la directory contiene un file di origine `Source.vb`denominato, è possibile compilarlo `vbc.exe Source.vb`digitando.

## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
