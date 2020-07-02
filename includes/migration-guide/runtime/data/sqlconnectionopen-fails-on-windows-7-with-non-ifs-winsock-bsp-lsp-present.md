---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622037"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>SqlConnection.Open non riesce in Windows 7 se sono presenti un provider LSP o BSP Winsock non IFS

#### <a name="details"></a>Dettagli

<xref:System.Data.SqlClient.SqlConnection.Open> e <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> hanno esito negativo in .NET Framework 4.5 se in esecuzione in un computer Windows 7 in cui sono presenti un provider LSP o BSP Winsock non IFS. Per determinare se è installato un provider LSP o BSP Winsock non IFS, usare il comando <code>netsh WinSock Show Catalog</code> ed esaminare ogni elemento <code>Winsock Catalog Provider Entry</code> restituito. Se per il valore Service Flags è impostato il bit <code>0x20000</code>, il provider usa handle IFS e funzionerà correttamente. Se il bit <code>0x20000</code> non è impostato, si tratta di un LSP o BSP non-IFS.

#### <a name="suggestion"></a>Suggerimento

Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework. In alternativa, è possibile evitarlo rimuovendo qualsiasi provider LSP Winsock non-IFS installato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
