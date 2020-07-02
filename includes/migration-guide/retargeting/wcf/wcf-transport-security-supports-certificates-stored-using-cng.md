---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614497"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>La sicurezza del trasporto WCF supporta i certificati archiviati usando CNG

#### <a name="details"></a>Dettagli

A partire dalle applicazioni che hanno come destinazione .NET Framework 4.6.2, la sicurezza del trasporto WCF supporta i certificati archiviati usando la libreria di crittografia di Windows (CNG). Questo supporto è limitato ai certificati con una chiave pubblica che ha un esponente di lunghezza non superiore a 32 bit. Quando un'applicazione è destinata a .NET Framework 4.6.2, questa funzionalità è attivata per impostazione predefinita. Nelle versioni precedenti di .NET Framework il tentativo di usare i certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione.

#### <a name="suggestion"></a>Suggerimento

Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma eseguite in .NET Framework 4.6.2 abilitano il supporto per i certificati CNG aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

L'operazione può essere eseguita anche con il codice seguente:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

Si noti che, grazie a questa modifica, i codici di gestione delle eccezioni che dipendono dal tentativo di avviare una comunicazione protetta con un certificato CNG di esito negativo non verranno più eseguiti.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6.2       |
| Type    | Ridestinazione |
