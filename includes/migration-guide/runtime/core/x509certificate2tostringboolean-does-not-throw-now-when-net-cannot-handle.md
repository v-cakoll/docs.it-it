---
ms.openlocfilehash: 0dfc87201b9b31cd9d936f2c965c7d0ca0140cab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858426"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean) ora non genera un'eccezione quando .NET non è in grado di gestire il certificato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5.2 e versioni precedenti, questo metodo generava un'eccezione se veniva passato il valore <code>true</code> per il parametro verbose e se erano presenti certificati installati non supportati da .NET Framework. Ora il metodo ha esito positivo e restituisce una stringa valida che omette le parti inaccessibili del certificato.|
|Suggerimento|È consigliabile aggiornare qualsiasi codice che dipende da <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> in modo da prevedere che la stringa restituita possa escludere alcuni dati del certificato, ad esempio la chiave pubblica, la chiave privata e le estensioni, in alcuni casi in cui l'API avrebbe precedentemente generato un'eccezione.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
