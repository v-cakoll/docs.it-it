---
title: Disabilitare la compatibilità con DPI in Visual Studio
description: Descrive le limitazioni di progettazione di Windows Form su schermi HDPI e come eseguire Visual Studio come un processo non compatibili con DPI.
ms.date: 04/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.custom: seoapril2019
ms.openlocfilehash: e52debea382033417afe0bd47f899af1666192bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181382"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Disabilitare la compatibilità con DPI in Visual Studio

Visual Studio è un punti per pollice (DPI) compatibile con applicazioni, ovvero le scale visualizzato automaticamente. Se un'applicazione indica che non è compatibile con DPI, il sistema operativo Ridimensiona l'applicazione come un'immagine bitmap. Questo comportamento è l'acronimo di virtualizzazione DPI. L'applicazione continua a ritenere che venga eseguito al 100% di ridimensionamento o pari a 96 dpi.

Questo articolo illustra le limitazioni di progettazione di Windows Form su schermi HDPI e come eseguire Visual Studio come un processo non compatibili con DPI.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>Finestra di progettazione Windows Form su schermi HDPI

Il **finestra di progettazione Windows Form** in Visual Studio non dispone di supporto del ridimensionamento. Questo causa problemi di visualizzazione quando si aprono alcuni moduli i **finestra di progettazione Windows Form** in punti per pollice (HDPI) monitoraggi. Per esempi, i controlli possono essere visualizzati a sovrapporsi come illustrato nell'immagine seguente:

![Progettazione di form di Windows sul monitor HDPI](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

Quando si apre un modulo nel **finestra di progettazione Windows Form** in Visual Studio su un monitor HDPI, Visual Studio visualizza un informativo barra gialla nella parte superiore della finestra di progettazione:

![Barra informativa di Visual Studio per riavviare in modalità non compatibili con DPI](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

Legge il messaggio **ridimensionamento dello schermo principale è impostato su 200% (192 dpi). Ciò potrebbe causare problemi di rendering nella finestra di progettazione.**

> [!NOTE]
> Questa barra informativa è stata introdotta in Visual Studio 2017 versione 15.8.

Se si non funzionano nella finestra di progettazione e non essere necessario modificare il layout del form, è possibile ignorare la barra informativa e continuare a lavorare nell'editor del codice o in altri tipi di finestre di progettazione. (È anche possibile [disabilitare le notifiche](#disable-notifications) in modo che la barra informativa non vengono ancora visualizzati.) Solo le **finestra di progettazione Windows Form** è interessato. Se è necessario lavorare nel **finestra di progettazione Windows Form**, nella sezione successiva consente [risolvere il problema](#to-resolve-the-display-problem).

## <a name="to-resolve-the-display-problem"></a>Per risolvere il problema di visualizzazione

Sono disponibili tre opzioni per risolvere il problema di visualizzazione:

1. [Riavviare Visual Studio come un processo non compatibili con DPI](#restart-visual-studio-as-a-dpi-unaware-process)
2. [Aggiungere una voce del Registro di sistema](#add-a-registry-entry)
3. [Impostare la visualizzazione delle impostazione al 100% la scalabilità](#set-your-display-scaling-setting-to-100)

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>Riavviare Visual Studio come un processo non compatibili con DPI

È possibile riavviare Visual Studio come un processo non compatibili con DPI selezionando l'opzione nella barra informativa gialla. Questo è il modo migliore la risoluzione del problema.

Quando Visual Studio viene eseguito come processo non compatibili con DPI, vengono risolti i problemi di layout della finestra di progettazione, ma i tipi di carattere può sembrare sfocati. Visual Studio visualizza un messaggio informativo giallo diverso quando viene eseguito come un processo non compatibili con DPI con la dicitura **Visual Studio è in esecuzione come processo non compatibili con DPI. Finestre di progettazione XAML e WPF non vengano visualizzati correttamente.** La barra informativo offre anche la possibilità **riavviare Visual Studio come un processo compatibile con DPI**.

> [!NOTE]
> - Se si fossero non ancorato finestre degli strumenti in Visual Studio quando è selezionata l'opzione per riavviare un processo non compatibili con DPI, può modificare la posizione di tali finestre degli strumenti.
> - Se si usa il profilo di Visual Basic predefinito, o se si dispone di **Salva nuovi progetti alla creazione** opzione deselezionata nel **Tools** > **opzioni**  >  **Progetti e soluzioni**, Visual Studio non è possibile riaprire il progetto quando si riavvia un processo non compatibili con DPI. Tuttavia, è possibile aprire il progetto scegliendo tale comando sotto **File** > **progetti e soluzioni recenti**.

È necessario riavviare Visual Studio come compatibili con DPI processo una volta completate le operazioni **finestra di progettazione Windows Form**. Quando viene eseguito come processo non compatibili con DPI, i tipi di carattere possono apparivano sfocate e potrebbero verificarsi problemi in altre finestre di progettazione, ad esempio la **finestra di progettazione XAML**. Se si chiude e riapre Visual Studio quando è in esecuzione in modalità non compatibili con DPI, diventa compatibili con DPI nuovamente. È anche possibile scegliere il **riavviare Visual Studio come un processo compatibile con DPI** opzione nella barra informativa.

### <a name="add-a-registry-entry"></a>Aggiungere una voce del Registro di sistema

Visual Studio è possibile contrassegnare come non compatibili con DPI modificando il Registro di sistema. Aprire **dell'Editor del Registro di sistema** e aggiungere una voce per il **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** sottochiave:

**Voce**: A seconda se si usa Visual Studio 2017 o 2019, usare uno dei valori seguenti:

- C:\Programmi\Microsoft file (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe
- C:\Programmi\Microsoft file (x86) \Microsoft Visual Studio\2019\Community\Common7\IDE\devenv.exe

> [!NOTE]
> Se si usa l'edizione Professional o Enterprise di Visual Studio, sostituire **Community** con **Professional** oppure **Enterprise** nella voce. Sostituire la lettera di unità in base alle esigenze.

**Tipo**: REG_SZ

**Valore**: DPIUNAWARE

> [!NOTE]
> Visual Studio rimane in modalità non compatibili con DPI finché non si rimuove la voce del Registro di sistema.

### <a name="set-your-display-scaling-setting-to-100"></a>Impostare la visualizzazione delle impostazione al 100% la scalabilità

Per impostare la visualizzazione del ridimensionamento di impostazione al 100% in Windows 10, digitare **impostazioni di visualizzazione** nell'attività della casella di ricerca e quindi selezionare **Modifica impostazioni dello schermo**. Nel **le impostazioni** impostare nella finestra **modificare le dimensioni del testo, App e altri elementi** al **100%**.

Impostazione dello schermo al 100% la scalabilità può essere inaccettabile, poiché l'interfaccia utente potrebbe rendere troppo piccolo per essere utilizzabile.

## <a name="disable-notifications"></a>Disabilitare le notifiche

È possibile scegliere di non ricevere una notifica di DPI scalabilità problemi in Visual Studio. Si potrebbe voler disabilitare le notifiche se non sono in uso nella finestra di progettazione, ad esempio.

Per disabilitare le notifiche, scegliere **degli strumenti** > **opzioni** per aprire la **opzioni** finestra di dialogo. Quindi, scegliere **finestra di progettazione Windows Form** > **generali**e impostare **le notifiche di ridimensionamento DPI** per **False**.

![Opzione di notifiche di Ridimensionamento in Visual Studio](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

Se si desidera abilitare nuovamente in un secondo momento le notifiche di ridimensionamento, impostare la proprietà su **True**.

## <a name="troubleshoot"></a>Risolvere i problemi

Se la transizione di compatibilità con DPI non funziona come previsto in Visual Studio, verificare se è presente il `dpiAwareness` valore il **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File esecuzione Options\devenv.exe**  sottochiave nell'Editor del Registro di sistema. Eliminare il valore, se presente.

## <a name="see-also"></a>Vedere anche

- [Ridimensionamento automatico in Windows Form](automatic-scaling-in-windows-forms.md)
