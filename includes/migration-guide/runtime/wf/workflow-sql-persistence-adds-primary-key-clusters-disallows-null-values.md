---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802452"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>La persistenza SQL del flusso di lavoro aggiunge cluster della chiave primaria e non consente i valori null in alcune colonne

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7 le tabelle create per SQL Workflow Instance Store (SWIS) dallo script SqlWorkflowInstanceStoreSchema.sql usano chiavi primarie cluster. Per questo motivo le identità non supportano i valori <code>null</code>. Questa modifica non altera il funzionamento di SWIS. Gli aggiornamenti sono stati apportati per supportare la replica transazionale di SQL Server.|
|Suggerimento|Per l'applicazione di questa modifica è necessario applicare il file con estensione sql SqlWorkflowInstanceStoreSchemaUpgrade.sql alle installazioni esistenti. Le nuove installazioni del database dispongono automaticamente della modifica.|
|Scope|Microsoft Edge|
|Versione|4.7|
|Type|Runtime|
