---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616261"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>Le classi di crittografia gestite non generano un'eccezione CryptographyException in modalità FIPS

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.2 e versioni precedenti le classi del provider del servizio di crittografia gestite, ad esempio <xref:System.Security.Cryptography.SHA256Managed>, generano un'eccezione <xref:System.Security.Cryptography.CryptographicException> quando le librerie di crittografia del sistema sono configurate in modalità FIPS. Queste eccezioni vengono generate perché le versioni gestite non sono state sottoposte alla certificazione FIPS (Federal Information Processing Standards) 140-2, nonché per bloccare gli algoritmi di crittografia che non sono stati approvati in base alle regole FIPS.  Poiché sono pochi gli sviluppatori che hanno i computer di sviluppo in modalità FIPS, queste eccezioni vengono spesso generate solo nei sistemi di produzione.Le applicazioni destinate a .NET Framework 4.8 e versioni successive passano automaticamente ai nuovi criteri, meno stretti, quindi in questi casi non viene più generata un'eccezione <xref:System.Security.Cryptography.CryptographicException> per impostazione predefinita. Al contrario, le classi di crittografia gestite reindirizzano le operazioni di crittografia a una libreria di crittografia del sistema. Questa modifica dei criteri rimuove in modo efficiente una differenza potenzialmente fuorviante tra ambienti di sviluppo e ambienti di produzione e rende possibile eseguire i componenti nativi e i componenti gestiti in base agli stessi criteri di crittografia.

#### <a name="suggestion"></a>Suggerimento

Se questo comportamento è indesiderato, è possibile rifiutarlo esplicitamente e ripristinare il comportamento precedente in modo che venga generata un'eccezione <xref:System.Security.Cryptography.CryptographicException> in modalità FIPS aggiungendo l'impostazione di configurazione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

Se l'applicazione è destinata a .NET Framework 4.7.2 o versioni precedenti, è possibile acconsentire esplicitamente a questa modifica aggiungendo l'impostazione di configurazione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.8         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
