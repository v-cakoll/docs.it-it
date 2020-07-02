---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614457"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>Miglioramenti di accessibilità ASP.NET in .NET Framework 4.7.1

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7.1, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio per supportare al meglio i clienti ASP.NET.  Sono incluse le modifiche seguenti:

- Modifiche per implementare pattern di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo Aggiungi campo nella procedura guidata DetailsView o la finestra di dialogo Configura ListView nella procedura guidata ListView.
- Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'Editor campi del pager di dati.
- Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo Campi nella procedura guidata Modifica campi del pager del controllo DataPager, la finestra di dialogo Configura ObjectContext o la finestra di dialogo Configura selezione dati della procedura guidata Configura origine dati.

#### <a name="suggestion"></a>Suggerimento

**Come accettare o rifiutare queste modifiche** Per poter usufruire di queste modifiche nella finestra di progettazione di Visual Studio, l'applicazione deve essere eseguita in .NET Framework 4.7.1 o versione successiva. L'applicazione Web può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Installare Visual Studio 2017 15.3 o versione successiva, che supporta le nuove funzionalità di accessibilità con l'opzione di AppContext seguente per impostazione predefinita.
- Rifiutare i comportamenti di accessibilità legacy aggiungendo l'`Switch.UseLegacyAccessibilityFeatures`opzione di AppContext alla sezione `<runtime>` del file di configurazione devenv.config e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su `true`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.1       |
| Type    | Ridestinazione |
