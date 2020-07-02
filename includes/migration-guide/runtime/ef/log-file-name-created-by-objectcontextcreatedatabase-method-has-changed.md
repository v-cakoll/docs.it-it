---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620314"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>Il nome del file di log creato dal metodo ObjectContext.CreateDatabase è stato modificato in base alle specifiche di SQL Server

#### <a name="details"></a>Dettagli

Quando il metodo <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> viene chiamato direttamente oppure tramite Code First con il provider SqlClient e un valore AttachDBFilename nella stringa di connessione, viene creato un file di log denominato nomefile_log.ldf invece di nomefile.ldf (dove nomefile è il nome del file specificato dal valore AttachDBFilename). Questa modifica migliora il debug fornendo un file di log il cui nome si basa sulle specifiche di SQL Server.

#### <a name="suggestion"></a>Suggerimento

Se il nome del file di log è importante per un'app, l'app deve essere aggiornata in modo da prevedere il formato nomefile_log.ldf standard.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
