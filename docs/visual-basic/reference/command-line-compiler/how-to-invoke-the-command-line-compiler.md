---
title: 'Procedura: richiamare il compilatore da riga di comando (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Procedura: richiamare il compilatore da riga di comando (Visual Basic)
È possibile richiamare il compilatore della riga di comando digitando il nome del file eseguibile nella riga di comando, noto anche come finestra MS-DOS. Se esegue la compilazione dal prompt dei comandi di Windows predefinito, è necessario digitare il percorso completo del file eseguibile. Per eseguire l'override di questo comportamento predefinito, è possibile utilizzare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi o modificare la variabile di ambiente PATH. Entrambi consentono di eseguire la compilazione da qualsiasi directory digitando il nome del compilatore.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Per richiamare il compilatore utilizzando il prompt dei comandi di Visual Studio  
  
1.  Aprire la cartella di programma strumenti di Visual Studio all'interno del gruppo di programmi Microsoft Visual Studio.  
  
2.  È possibile utilizzare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi per accedere al compilatore da qualsiasi directory sul computer, se è installato Visual Studio.  
  
3.  Richiamare il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] prompt dei comandi.  
  
4.  Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.  
  
     Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory. Se la directory contiene un file di origine denominato `Source.vb`, sarebbe possibile compilarlo digitando `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Per impostare la variabile di ambiente PATH per il compilatore per il prompt dei comandi di Windows  
  
1.  Utilizzare la funzionalità di ricerca di Windows per trovare Vbc.exe sul disco locale.  
  
     Il nome esatto della directory in cui si trova il compilatore dipende dal percorso della directory di Windows e la versione di "Installato .NET Framework". Se si dispone di più di una versione di "Installato .NET Framework", è necessario determinare la versione da usare (in genere la versione più recente).  
  
2.  Dal **avviare** Menu, fare doppio clic su **risorse del Computer**e quindi fare clic su **proprietà** dal menu di scelta rapida.  
  
3.  Fare clic su di **avanzate** scheda e quindi fare clic su **le variabili di ambiente**.  
  
4.  Nel **sistema** riquadro variabili, seleziona **percorso** dall'elenco e fare clic su **modifica**.  
  
5.  Nel **modifica sistema** variabili della finestra di dialogo spostare il punto di inserimento alla fine della stringa nel **valore della variabile** campo e digitare un punto e virgola (;) seguito dal nome completo della directory trovato nel passaggio 1.  
  
6.  Fare clic su **OK** per confermare le modifiche e chiudere le finestre di dialogo.  
  
     Dopo aver modificato la variabile di ambiente PATH, è possibile eseguire il compilatore Visual Basic nel prompt dei comandi di Windows da qualsiasi directory nel computer.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Per richiamare il compilatore utilizzando il prompt dei comandi di Windows  
  
1.  Dal **avviare** menu, fare clic su di **Accessori** cartella e quindi aprire il **prompt dei comandi di Windows**.  
  
2.  Nella riga di comando, digitare `vbc.exe` *sourceFileName* e quindi premere INVIO.  
  
     Ad esempio, se il codice sorgente è memorizzato in una directory denominata `SourceFiles`, viene aperto il prompt dei comandi e il tipo `cd SourceFiles` per passare a tale directory. Se la directory contiene un file di origine denominato `Source.vb`, sarebbe possibile compilarlo digitando `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
