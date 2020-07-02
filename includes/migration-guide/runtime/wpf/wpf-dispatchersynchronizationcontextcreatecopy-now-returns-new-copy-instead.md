---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620461"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>DispatcherSynchronizationContext.CreateCopy di WPF ora restituisce una nuova copia anziché l'istanza corrente

#### <a name="details"></a>Dettagli

In .NET Framework 4 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> restituiva un riferimento all'istanza corrente, principalmente come ottimizzazione delle prestazioni. In .NET Framework 4.5 restituisce una nuova istanza che rende possibile per la prima volta concludere che riferimenti uguali indicano che il thread in esecuzione è nel contesto di sincronizzazione corretto.  È improbabile che ciò influisca sul codice che verifica l'identità di questi riferimenti, ma a causa della modifica è opportuno testare il codice che chiama <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> nell'ambito della migrazione a .NET Framework 4.5 o versione successiva.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> ora restituirà un nuovo oggetto <xref:System.Threading.SynchronizationContext?displayProperty=fullName>. Nelle versioni precedenti il codice che usa l'equivalenza dei riferimenti generati in questo modo non controlla in effetti se il contesto attivo è corretto, ma questa verifica viene eseguita quando il codice viene compilato per .NET Framework 4.5 o versione successiva.  Anche se è improbabile che si verifichino problemi, il test dei percorsi del codice interessati dovrebbe essere sufficiente per determinare se ciò costituisce un problema.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
