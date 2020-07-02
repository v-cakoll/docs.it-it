---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621247"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>La persistenza SQL del flusso di lavoro aggiunge cluster della chiave primaria e non consente i valori null in alcune colonne

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7 le tabelle create per SQL Workflow Instance Store (SWIS) dallo script SqlWorkflowInstanceStoreSchema.sql usano chiavi primarie cluster. Per questo motivo le identità non supportano i valori <code>null</code>. Questa modifica non altera il funzionamento di SWIS. Gli aggiornamenti sono stati apportati per supportare la replica transazionale di SQL Server.

#### <a name="suggestion"></a>Suggerimento

Per l'applicazione di questa modifica è necessario applicare il file con estensione sql SqlWorkflowInstanceStoreSchemaUpgrade.sql alle installazioni esistenti. Le nuove installazioni del database dispongono automaticamente della modifica.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7|
|Type|Runtime|
