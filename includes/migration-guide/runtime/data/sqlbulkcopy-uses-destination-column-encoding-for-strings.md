---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620281"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy usa la codifica della colonna di destinazione per le stringhe

#### <a name="details"></a>Dettagli

Nell'inserire i dati in una colonna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> usa la codifica della colonna di destinazione anziché quella predefinita per i tipi <code>VARCHAR</code> e <code>CHAR</code>. Questa modifica elimina la possibilità di danneggiamento dei dati causata dall'uso della codifica predefinita quando questa non viene usata dalla colonna di destinazione. In rari casi, un'applicazione esistente può generare un'eccezione SqlException se la modifica nella codifica produce dati troppo grandi per rientrare nella colonna di destinazione.

#### <a name="suggestion"></a>Suggerimento

<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> non danneggerà più i dati a causa di differenze di codifica. Se vengono copiate stringhe prossime al limite delle dimensioni della colonna di destinazione, può essere necessario pre-codificare i dati (copiarli per verificare che rientrino nella colonna di destinazione) o rilevare eccezioni <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
