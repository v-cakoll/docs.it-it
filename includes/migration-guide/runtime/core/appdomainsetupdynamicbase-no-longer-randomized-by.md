---
ms.openlocfilehash: 3f553f95941eaf36cf335e9765a670a05bd157f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858619"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>Il valore AppDomainSetup.DynamicBase non è più generato in modo casuale da UseRandomizedStringHashAlgorithm

|   |   |
|---|---|
|Dettagli|Prima di .NET Framework 4.6, il valore di <xref:System.AppDomainSetup.DynamicBase> sarebbe stato casuale tra i domini applicazione o tra i processi con l'impostazione UseRandomizedStringHashAlgorithm abilitata nel file di configurazione dell'app. A partire da .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> restituirà un risultato stabile tra istanze diverse di un'app in esecuzione e tra domini app diversi. Le basi dinamiche saranno comunque diverse per app differenti. Questa modifica rimuove solo l'elemento di denominazione casuale per le diverse istanze della stessa app.|
|Suggerimento|Tenere presente che l'abilitazione di <code>UseRandomizedStringHashAlgorithm</code> non comporterà la generazione casuale di <xref:System.AppDomainSetup.DynamicBase>. Se è necessaria una base casuale, devono essere prodotta nel codice dell'app invece che tramite questa API.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Runtime|
|API interessate|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
