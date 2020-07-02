---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617238"
---
### <a name="xml-schema-validation-is-stricter"></a>La convalida di XML Schema è più rigida

#### <a name="details"></a>Dettagli

In .NET Framework 4.5 la convalida XML Schema è più rigida. Se si usa xsd:anyURI per convalidare un URI, come un protocollo mailto, la convalida ha esito negativo se sono presenti spazi nell'URI. Nelle versioni precedenti di .NET Framework la convalida aveva esito positivo. La modifica influisce solo sulle applicazioni destinate a .NET Framework 4.5.

#### <a name="suggestion"></a>Suggerimento

Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.0 di .NET Framework. In caso di ridestinazione a .NET Framework 4.5, tuttavia, è necessario rivedere il codice per assicurarsi che gli URI non validi (con spazi) non siano previsti come valori di attributo con il tipo di dati anyURI.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5         |
| Type    | Ridestinazione |
