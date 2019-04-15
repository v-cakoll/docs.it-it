---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236241"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>La persistenza SQL del flusso di lavoro aggiunge cluster della chiave primaria e non consente i valori null in alcune colonne

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7 le tabelle create per SQL Workflow Instance Store (SWIS) dallo script SqlWorkflowInstanceStoreSchema.sql usano chiavi primarie cluster. Per questo motivo le identità non supportano i valori <code>null</code>. Questa modifica non altera il funzionamento di SWIS. Gli aggiornamenti sono stati apportati per supportare la replica transazionale di SQL Server.|
|Suggerimento|Per l'applicazione di questa modifica è necessario applicare il file con estensione sql SqlWorkflowInstanceStoreSchemaUpgrade.sql alle installazioni esistenti. Le nuove installazioni del database dispongono automaticamente della modifica.|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Runtime|
