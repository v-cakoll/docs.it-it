---
title: 'Procedura: compilare in modo condizionale con traccia e debug'
ms.date: 03/30/2017
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
ms.openlocfilehash: 2c3ec54535319f4c7507563a5976038ca40d20aa
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217460"
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a>Procedura: compilare in modo condizionale con traccia e debug
Quando si sottopone a debug l'applicazione durante la fase di sviluppo, sia l'output di tracciatura che l'output di debug vengono inviati alla finestra di output in Visual Studio. Tuttavia, per includere funzionalità di tracciatura in un'applicazione distribuita, è necessario compilare le applicazioni instrumentate con la direttiva del compilatore **TRACE** abilitata. In questo modo è possibile tracciare il codice da compilare nella versione di rilascio dell'applicazione. Se non si abilita la direttiva **TRACE**, tutto il codice di tracciatura verrà ignorato durante la compilazione e non sarà incluso nel codice eseguibile da distribuire.  
  
 Sia i metodi di debug che di tracciatura sono dotati di attributi condizionali associati. Ad esempio, se l'attributo condizionale per la traccia è **true**, tutte le istruzioni di traccia verranno incluse all'interno di un assembly, ovvero un file EXE o DLL compilato. Se l'attributo condizionale **Trace** è **false**, le istruzioni di traccia non verranno incluse.  
  
 In una build è possibile attivare uno degli attributi condizionali **Trace** o **Debug**, entrambi gli attributi o nessuno. Esistono quindi quattro tipi di build: **Debug**, **Trace**, entrambi o nessuno. Alcune build di rilascio per la distribuzione della produzione non contengono alcun attributo.  
  
 Le impostazioni del compilatore per l'applicazione possono essere specificate in diversi modi:  
  
- Pagine delle proprietà  
  
- Riga di comando  
  
- **#CONST** (per Visual Basic) e **#define** (per C#)  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a>Per modificare le impostazioni di compilazione dalla finestra di dialogo delle pagine delle proprietà  
  
1. Fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni**.  
  
2. Scegliere **Proprietà** dal menu di scelta rapida.  
  
    - In Visual Basic fare clic sulla scheda **Compila** nel riquadro sinistro della pagina delle proprietà e quindi fare clic sul pulsante **Opzioni di compilazione avanzate** per visualizzare la finestra di dialogo **Impostazioni del compilatore avanzate**. Selezionare le caselle di controllo per le impostazioni del compilatore che si vogliono attivare. Deselezionare le caselle di controllo per le impostazioni che si vogliono disabilitare.  
  
    - In C# fare clic sulla scheda **Compila** nel riquadro sinistro della pagina delle proprietà e quindi selezionare le caselle di controllo per le impostazioni del compilatore che si vogliono abilitare. Deselezionare le caselle di controllo per le impostazioni che si vogliono disabilitare.  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a>Per compilare il codice instrumentato usando la riga di comando  
  
1. Impostare un'opzione del compilatore condizionale sulla riga di comando. Il compilatore includerà il codice di traccia o di debug nell'eseguibile.  
  
     Ad esempio, l'istruzione del compilatore che segue, immessa sulla riga di comando, includerà il codice di tracciatura in un eseguibile compilato:  
  
     Per Visual Basic: **vbc-r:System.dll-d:Trace = true-d:debug = false MyApplication. vb**  
  
     Per C#: **csc-r:System.dll-d:Trace-d:debug = false MyApplication.cs**  
  
    > [!TIP]
    > Per compilare più file dell'applicazione, lasciare uno spazio vuoto tra i nomi dei file, ad esempio: **MyApplication1.vb MyApplication2.vb MyApplication3.vb** o **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.  
  
     Il significato delle direttive di compilazione condizionale usate nell'esempio precedente è riportato di seguito:  
  
    |Direttiva|Significato|  
    |---------------|-------------|  
    |`vbc`|Visual Basic (compilatore)|  
    |`csc`|Compilatore C#|  
    |`-r:`|Riferimenti a un assembly esterno (EXE o DLL)|  
    |`-d:`|Definizione di un simbolo di compilazione condizionale|  
  
    > [!NOTE]
    > È necessario scrivere TRACE o DEBUG con le lettere maiuscole. Per altre informazioni sui comandi di compilazione condizionale, immettere `vbc /?` (per Visual Basic) o `csc /?` (per C#) al prompt dei comandi. Per altre informazioni, vedere [Compilazione dalla riga di comando (C#)](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) o [Utilizzo del compilatore dalla riga di comando (Visual Basic)](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md).  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a>Per eseguire la compilazione condizionale con #CONST o #define  
  
1. Digitare l'istruzione adatta per il linguaggio di programmazione usato all'inizio del file di codice sorgente.  
  
    |Linguaggio|.|Risultato|  
    |--------------|---------------|------------|  
    |**Visual Basic**|**#CONST TRACE = true**|Abilita la traccia|  
    ||**#CONST TRACE = false**|Disabilita la traccia|  
    ||**#CONST DEBUG = true**|Attiva il debug|  
    ||**#CONST DEBUG = false**|Disabilita il debug|  
    |**C#**|**#define TRACE**|Abilita la traccia|  
    ||**#undef TRACE**|Disabilita la traccia|  
    ||**#define DEBUG**|Attiva il debug|  
    ||**#undef DEBUG**|Disabilita il debug|  
  
### <a name="to-disable-tracing-or-debugging"></a>Per disabilitare la traccia o il debug  
  
Eliminare la direttiva del compilatore dal codice sorgente.  
  
\- - oppure -  
  
Impostare come commento la direttiva del compilatore.  
  
> [!NOTE]
> Al momento di avviare la compilazione è possibile scegliere **Compila** dal menu **Compila** o usare il metodo della riga di comando senza digitare **d:** per definire i simboli di compilazione condizionale.  
  
## <a name="see-also"></a>Vedere anche

- [Traccia e strumentazione di applicazioni](tracing-and-instrumenting-applications.md)
- [Procedura: Creare, inizializzare e configurare opzioni di traccia](how-to-create-initialize-and-configure-trace-switches.md)
- [Opzioni di traccia](trace-switches.md)
- [Listener di traccia](trace-listeners.md)
- [Procedura: aggiungere istruzioni di traccia al codice dell'applicazione](how-to-add-trace-statements-to-application-code.md)
- [Come impostare le variabili di ambiente per la riga di comando di Visual Studio](../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [Procedura:Richiamare il compilatore da riga di comando](../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)
