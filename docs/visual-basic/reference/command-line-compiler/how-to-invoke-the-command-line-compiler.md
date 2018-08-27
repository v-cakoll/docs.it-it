---
title: 'Procedura: richiamare il compilatore da riga di comando (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 0b835bb5654574a5aa6f32eede1e942b11e7dcb0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932154"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Procedura: richiamare il compilatore da riga di comando (Visual Basic)
È possibile richiamare il compilatore della riga di comando digitando il nome del relativo file eseguibile nella riga di comando, noto anche come il prompt dei comandi MS-DOS. Se si esegue la compilazione dal prompt dei comandi di Windows predefinito, è necessario digitare il percorso completo del file eseguibile. Per eseguire l'override di questo comportamento predefinito, è possibile usare il prompt dei comandi di Visual Studio, o modificare la variabile di ambiente PATH. Entrambi consentono di compilare da qualsiasi directory, è sufficiente digitare il nome del compilatore.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Per richiamare il compilatore utilizzando il prompt dei comandi di Visual Studio  
  
1.  Aprire la cartella di programma strumenti di Visual Studio all'interno del gruppo di programmi Microsoft Visual Studio.  
  
2.  È possibile usare il prompt dei comandi di Visual Studio per accedere al compilatore da qualsiasi directory nel computer, se è installato Visual Studio.  
  
3.  Richiamare il prompt dei comandi di Visual Studio.  
  
4.  Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.  
  
     Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory. Se la directory contiene un file di origine denominato `Source.vb`, è possibile compilarlo digitando `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Per impostare la variabile di ambiente PATH al compilatore per il prompt dei comandi di Windows  
  
1.  Usare la funzionalità di Windows Search per trovare Vbc.exe sul disco locale.  
  
     Il nome esatto della directory in cui si trova il compilatore dipende la posizione della directory di Windows e la versione di "Installato .NET Framework". Se si dispone di più di una versione di ".NET Framework" installato, è necessario determinare la versione da usare (in genere la versione più recente).  
  
2.  Dalle **avviare** Menu, fare doppio clic su **risorse del Computer**e quindi fare clic su **proprietà** dal menu di scelta rapida.  
  
3.  Scegliere il **avanzate** scheda e quindi fare clic su **variabili di ambiente**.  
  
4.  Nel **System** riquadro variabili, seleziona **Path** dall'elenco e fare clic su **modifica**.  
  
5.  Nel **modifica sistema** sposta il punto di inserimento alla fine della stringa nella finestra di dialogo variabile il **il valore della variabile** campo e digitare un punto e virgola (;) seguito dal nome completo della directory trovato nel passaggio 1.  
  
6.  Fare clic su **OK** per confermare le modifiche e chiudere le finestre di dialogo.  
  
     Dopo aver modificato la variabile di ambiente PATH, è possibile eseguire il compilatore Visual Basic al prompt dei comandi di Windows da qualsiasi directory nel computer.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Per richiamare il compilatore utilizzando il prompt dei comandi di Windows  
  
1.  Dal **avviare** menu, fare clic sui **Accessori** cartella e quindi aprire il **prompt dei comandi di Windows**.  
  
2.  Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.  
  
     Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory. Se la directory contiene un file di origine denominato `Source.vb`, è possibile compilarlo digitando `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
