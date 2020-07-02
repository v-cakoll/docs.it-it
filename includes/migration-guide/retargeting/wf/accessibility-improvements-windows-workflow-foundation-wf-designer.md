---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614854"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Miglioramenti di accessibilità in Progettazione flussi di lavoro di Windows Workflow Foundation (WF)

#### <a name="details"></a>Dettagli

Progettazione flussi di lavoro di Windows Workflow Foundation (WF) è stata migliorata per poter usare tecnologie di accessibilità. Questi miglioramenti includono le modifiche seguenti:

- L'ordine di tabulazione viene modificato da sinistra a destra e dall'alto verso il basso in alcuni controlli:
- Finestra di inizializzazione della correlazione in cui impostare i dati di correlazione per l'attività <xref:System.ServiceModel.Activities.InitializeCorrelation>
- Finestra di definizione del contenuto per le attività <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>
- Altre funzioni sono disponibili tramite tastiera:
- Quando vengono modificate le proprietà di un'attività, i gruppi delle proprietà possono essere compressi tramite tastiera la prima volta che hanno lo stato attivo.
- Le icone di avviso ora sono accessibili dalla tastiera.
- Il pulsante Altre proprietà nella finestra Proprietà è ora accessibile dalla tastiera.
- Tramite tastiera gli utenti ora possono accedere agli elementi dell'intestazione nei riquadri Argomenti e Variabili in Progettazione flussi di lavoro.
- Maggiore visibilità degli elementi con stato attivo, ad esempio quando:
- Aggiunta di righe alle griglie di dati usate in Progettazione flussi di lavoro e in ActivityDesigner.
- Tabulazione all'interno dei campi nelle attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>.
- Impostazione di valori predefiniti per variabili o argomenti
- Le utilità per la lettura dello schermo ora possono riconoscere correttamente:
- Set di punti di interruzione in Progettazione flussi di lavoro.
- Attività <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> e <xref:System.ServiceModel.Activities.CorrelationScope>.
- Contenuto dell'attività <xref:System.ServiceModel.Activities.Receive>.
- Tipo di destinazione per l'attività <xref:System.Activities.Statements.InvokeMethod>.
- Casella combinata Eccezione e sezione Finally nell'attività <xref:System.Activities.Statements.TryCatch>.
- Casella combinata Tipo di messaggio, barra di divisione nella finestra Aggiungi inizializzatori di correlazione, finestra Content Definition (Definizione contenuto) e finestra Definizione di CorrelatesOn nelle attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>).
- Transizioni della macchina a uno stato e destinazioni delle transazioni.
- Annotazioni e connettori nelle attività <xref:System.Activities.Statements.FlowDecision>.
- Menu di scelta rapida per le attività.
- Editor di valori di proprietà, pulsante Cancella ricerca, pulsanti di ordinamento Per categoria e In ordine alfabetico e finestra di dialogo Editor espressioni nella griglia delle proprietà.
- Percentuale di zoom in Progettazione flussi di lavoro.
- Separatore nelle attività <xref:System.Activities.Statements.Parallel> e <xref:System.Activities.Statements.Pick>.
- Attività <xref:System.Activities.Statements.InvokeDelegate>.
- Finestra Seleziona tipi per le attività di dizionario (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>` e così via).
- Finestra Cerca e seleziona un tipo .NET.
- Navigazioni in Progettazione flussi di lavoro.
- Gli utenti che usano i temi a contrasto elevato noteranno molti miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di riepilogo più evidenti per gli elementi con lo stato attivo.

#### <a name="suggestion"></a>Suggerimento

Se Progettazione flussi di lavoro è stata riallocata nell'applicazione, l'applicazione può usufruire dei vantaggi offerti da queste modifiche eseguendo una delle azioni seguenti:

- Ricompilare l'applicazione per usare .NET Framework 4.7.1. Queste modifiche di accessibilità sono abilitate per impostazione predefinita.
- Se l'applicazione usa .NET Framework 4.7 o versione precedente, ma viene eseguita in .NET Framework 4.7.1, è possibile rifiutare questi comportamenti di accessibilità legacy aggiungendo l'[opzione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.1       |
| Type    | Ridestinazione |
