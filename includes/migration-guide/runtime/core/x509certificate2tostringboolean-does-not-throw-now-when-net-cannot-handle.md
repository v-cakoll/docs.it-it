---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858426"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean) ora non genera un'eccezione quando .NET non è in grado di gestire il certificato

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5.2 e versioni precedenti, questo metodo generava un'eccezione se veniva passato il valore <code>true</code> per il parametro verbose e se erano presenti certificati installati non supportati da .NET Framework. Ora il metodo ha esito positivo e restituisce una stringa valida che omette le parti inaccessibili del certificato.|
|Suggerimento|È consigliabile aggiornare qualsiasi codice che dipende da <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> in modo da prevedere che la stringa restituita possa escludere alcuni dati del certificato, ad esempio la chiave pubblica, la chiave privata e le estensioni, in alcuni casi in cui l'API avrebbe precedentemente generato un'eccezione.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

