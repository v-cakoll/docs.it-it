---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621292"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>Il valore AppDomainSetup.DynamicBase non è più generato in modo casuale da UseRandomizedStringHashAlgorithm

#### <a name="details"></a>Dettagli

Prima di .NET Framework 4.6, il valore di <xref:System.AppDomainSetup.DynamicBase> sarebbe stato casuale tra i domini applicazione o tra i processi con l'impostazione UseRandomizedStringHashAlgorithm abilitata nel file di configurazione dell'app. A partire da .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> restituirà un risultato stabile tra istanze diverse di un'app in esecuzione e tra domini app diversi. Le basi dinamiche saranno comunque diverse per app differenti. Questa modifica rimuove solo l'elemento di denominazione casuale per le diverse istanze della stessa app.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che l'abilitazione di <code>UseRandomizedStringHashAlgorithm</code> non comporterà la generazione casuale di <xref:System.AppDomainSetup.DynamicBase>. Se è necessaria una base casuale, devono essere prodotta nel codice dell'app invece che tramite questa API.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
