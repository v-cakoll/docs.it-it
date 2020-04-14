---
ms.openlocfilehash: fa2a856911c7dcf81a39b7682a62a86c35328037
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275461"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a>L'oggetto AddressHeaderCollection di WCF ora genera un'eccezione ArgumentException se un elemento addressHeader è Null

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1 il costruttore <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> genera un'eccezione <xref:System.ArgumentException> se uno degli elementi è <code>null</code>. In .NET Framework 4.7 e versioni precedenti non viene generata alcuna eccezione.|
|Suggerimento|Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Runtime|
|API interessate|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
