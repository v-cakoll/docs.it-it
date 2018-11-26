---
title: Disabilitare la compatibilità con DPI in Visual Studio
description: Descrive le limitazioni di progettazione form di Windows su schermi HDPI e su come eseguire Visual Studio come un processo non compatibili con DPI.
ms.date: 08/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 2d3466476c33a3e5faa8be96d63f1d11442c5d70
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296737"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Disabilitare la compatibilità con DPI in Visual Studio

Visual Studio è un punti per pollice (DPI) compatibile con applicazioni, ovvero le scale visualizzato automaticamente. Se un'applicazione indica che non è compatibile con DPI, il sistema operativo Ridimensiona l'applicazione come un'immagine bitmap. Questo comportamento è l'acronimo di virtualizzazione DPI. L'applicazione continua a ritenere che venga eseguito al 100% di ridimensionamento o pari a 96 dpi.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>Finestra di progettazione Windows Form su schermi HDPI

Il **finestra di progettazione Windows Form** in Visual Studio non dispone di supporto del ridimensionamento. Questo causa problemi di visualizzazione quando si aprono alcuni moduli i **finestra di progettazione Windows Form** in punti per pollice (HDPI) monitoraggi. Per esempi, i controlli possono essere visualizzati a sovrapporsi come illustrato nell'immagine seguente:

![Progettazione di form di Windows sul monitor HDPI](media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

In Visual Studio 2017 versione 15,8 e versioni successive, quando si apre un modulo nel **finestra di progettazione Windows Form** su un monitor HDPI, Visual Studio visualizza un informativo barra gialla nella parte superiore della finestra di progettazione:

![Barra informativa di Visual Studio per riavviare in modalità non compatibili con DPI](media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

Legge il messaggio **ridimensionamento dello schermo principale è impostato su 200% (192 dpi). Ciò potrebbe causare problemi di rendering nella finestra di progettazione.**

Se si non funzionano nella finestra di progettazione e non essere necessario modificare il layout del form, è possibile ignorare la barra informativa e continuare a lavorare nell'editor del codice o in altri tipi di finestre di progettazione. Solo le **finestra di progettazione Windows Form** è interessato. Se è necessario lavorare nel **finestra di progettazione Windows Form**, nella sezione successiva consente [risolvere il problema](#to-resolve-the-problem).

## <a name="to-resolve-the-problem"></a>Per risolvere il problema

Sono disponibili tre opzioni per risolvere il problema di visualizzazione.

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>Riavviare Visual Studio come un processo non compatibili con DPI

È possibile riavviare Visual Studio come un processo non compatibili con DPI selezionando l'opzione nella barra informativa gialla. Questo è il modo migliore la risoluzione del problema.

Quando Visual Studio viene eseguito come processo non compatibili con DPI, vengono risolti i problemi di layout della finestra di progettazione, ma i tipi di carattere può sembrare sfocati. Visual Studio visualizza un messaggio informativo giallo diverso quando viene eseguito come un processo non compatibili con DPI con la dicitura **Visual Studio è in esecuzione come processo non compatibili con DPI. Finestre di progettazione XAML e WPF non vengano visualizzati correttamente.** La barra informativo offre anche la possibilità **riavviare Visual Studio come un processo compatibile con DPI**.

> [!NOTE]
> - Se si fossero non ancorato finestre degli strumenti in Visual Studio quando è selezionata l'opzione per riavviare un processo non compatibili con DPI, può modificare la posizione di tali finestre degli strumenti.
> - Se si usa il profilo di Visual Basic predefinito, o se si dispone di **Salva nuovi progetti alla creazione** opzione deselezionata nel **Tools** > **opzioni**  >  **Progetti e soluzioni**, Visual Studio non è possibile riaprire il progetto quando si riavvia un processo non compatibili con DPI. Tuttavia, è possibile aprire il progetto scegliendo tale comando sotto **File** > **progetti e soluzioni recenti**.

È necessario riavviare Visual Studio come compatibili con DPI processo una volta completate le operazioni **finestra di progettazione Windows Form**. Quando viene eseguito come processo non compatibili con DPI, i tipi di carattere possono apparivano sfocate e potrebbero verificarsi problemi in altre finestre di progettazione, ad esempio la **finestra di progettazione XAML**. Se si chiude e riapre Visual Studio quando è in esecuzione in modalità non compatibili con DPI, diventa compatibili con DPI nuovamente. È anche possibile scegliere il **riavviare Visual Studio come un processo compatibile con DPI** opzione nella barra informativa.

### <a name="add-a-registry-entry"></a>Aggiungere una voce del Registro di sistema

Visual Studio è possibile contrassegnare come non compatibili con DPI modificando il Registro di sistema. Aprire **dell'Editor del Registro di sistema** e aggiungere una voce per il **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** sottochiave:

**Voce**: c:\Programmi\Microsoft file (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe

   > [!NOTE]
   > Se si usa l'edizione Professional o Enterprise di Visual Studio 2017, sostituire **Community** con **Professional** oppure **Enterprise** nella voce. Sostituire la lettera di unità in base alle esigenze.

**Tipo**: REG_SZ

**Valore**: DPIUNAWARE

> [!NOTE]
> Visual Studio rimane in modalità non compatibili con DPI finché non si rimuove la voce del Registro di sistema.

### <a name="set-your-display-scaling-setting-to-100"></a>Impostare la visualizzazione delle impostazione al 100% la scalabilità

Per impostare la visualizzazione del ridimensionamento di impostazione al 100% in Windows 10, digitare **impostazioni di visualizzazione** nell'attività della casella di ricerca e quindi selezionare **Modifica impostazioni dello schermo**. Nel **le impostazioni** impostare nella finestra **modificare le dimensioni del testo, App e altri elementi** al **100%**.

Impostazione dello schermo al 100% la scalabilità può essere inaccettabile, poiché l'interfaccia utente potrebbe rendere troppo piccolo per essere utilizzabile.

## <a name="troubleshoot"></a>Risolvere i problemi

Se la transizione di compatibilità con DPI non funziona come previsto in Visual Studio, verificare se è presente il `dpiAwareness` valore il **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File esecuzione Options\devenv.exe**  sottochiave nell'Editor del Registro di sistema. Eliminare il valore, se presente.

## <a name="see-also"></a>Vedere anche

- [Ridimensionamento automatico in Windows Form](automatic-scaling-in-windows-forms.md)
