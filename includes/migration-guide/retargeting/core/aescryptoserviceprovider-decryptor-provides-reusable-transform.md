---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614441"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>Il componente di decrittografia AesCryptoServiceProvider fornisce una trasformazione riutilizzabile

#### <a name="details"></a>Dettagli

A partire dalle app destinate a .NET Framework 4.6.2, il componente di decrittografia <xref:System.Security.Cryptography.AesCryptoServiceProvider> fornisce una trasformazione riutilizzabile. Dopo una chiamata a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, la trasformazione viene reinizializzata e può essere riutilizzata. Per le app destinate a versioni precedenti di .NET Framework, il tentativo di riusare il componente di decrittografia chiamando <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> dopo una chiamata a <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> genera un'eccezione <xref:System.Security.Cryptography.CryptographicException> o produce dati danneggiati.

#### <a name="suggestion"></a>Suggerimento

L'impatto di questa modifica dovrebbe essere minimo, dato che questo è il comportamento previsto. Le applicazioni che dipendono dal comportamento precedente lo possono rifiutare esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

Le applicazioni destinate a versioni precedenti di .NET Framework ma in esecuzione su una versione uguale o successiva a .NET Framework .NET Framework 4.6.2 possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
