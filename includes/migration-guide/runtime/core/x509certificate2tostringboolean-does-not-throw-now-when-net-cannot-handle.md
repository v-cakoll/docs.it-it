---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621319"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean) ora non genera un'eccezione quando .NET non è in grado di gestire il certificato

#### <a name="details"></a>Dettagli

In .NET Framework 4.5.2 e versioni precedenti, questo metodo generava un'eccezione se veniva passato il valore <code>true</code> per il parametro verbose e se erano presenti certificati installati non supportati da .NET Framework. Ora il metodo ha esito positivo e restituisce una stringa valida che omette le parti inaccessibili del certificato.

#### <a name="suggestion"></a>Suggerimento

È consigliabile aggiornare qualsiasi codice che dipende da <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> in modo da prevedere che la stringa restituita possa escludere alcuni dati del certificato, ad esempio la chiave pubblica, la chiave privata e le estensioni, in alcuni casi in cui l'API avrebbe precedentemente generato un'eccezione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
