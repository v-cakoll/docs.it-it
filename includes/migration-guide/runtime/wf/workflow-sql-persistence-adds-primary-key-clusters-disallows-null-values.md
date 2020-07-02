---
ms.openlocfilehash: 809ca85b347fabc44573e2e0c5a43261d68590d3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621247"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="38cde-101">La persistenza SQL del flusso di lavoro aggiunge cluster della chiave primaria e non consente i valori null in alcune colonne</span><span class="sxs-lookup"><span data-stu-id="38cde-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

#### <a name="details"></a><span data-ttu-id="38cde-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="38cde-102">Details</span></span>

<span data-ttu-id="38cde-103">A partire da .NET Framework 4.7 le tabelle create per SQL Workflow Instance Store (SWIS) dallo script SqlWorkflowInstanceStoreSchema.sql usano chiavi primarie cluster.</span><span class="sxs-lookup"><span data-stu-id="38cde-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="38cde-104">Per questo motivo le identità non supportano i valori <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="38cde-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="38cde-105">Questa modifica non altera il funzionamento di SWIS.</span><span class="sxs-lookup"><span data-stu-id="38cde-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="38cde-106">Gli aggiornamenti sono stati apportati per supportare la replica transazionale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38cde-106">The updates were made to support SQL Server Transactional Replication.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="38cde-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="38cde-107">Suggestion</span></span>

<span data-ttu-id="38cde-108">Per l'applicazione di questa modifica è necessario applicare il file con estensione sql SqlWorkflowInstanceStoreSchemaUpgrade.sql alle installazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="38cde-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="38cde-109">Le nuove installazioni del database dispongono automaticamente della modifica.</span><span class="sxs-lookup"><span data-stu-id="38cde-109">New database installations will automatically have the change.</span></span>

| <span data-ttu-id="38cde-110">Nome</span><span class="sxs-lookup"><span data-stu-id="38cde-110">Name</span></span>    | <span data-ttu-id="38cde-111">Valore</span><span class="sxs-lookup"><span data-stu-id="38cde-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="38cde-112">Scope</span><span class="sxs-lookup"><span data-stu-id="38cde-112">Scope</span></span>   |<span data-ttu-id="38cde-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="38cde-113">Edge</span></span>|
|<span data-ttu-id="38cde-114">Version</span><span class="sxs-lookup"><span data-stu-id="38cde-114">Version</span></span>|<span data-ttu-id="38cde-115">4.7</span><span class="sxs-lookup"><span data-stu-id="38cde-115">4.7</span></span>|
|<span data-ttu-id="38cde-116">Type</span><span class="sxs-lookup"><span data-stu-id="38cde-116">Type</span></span>|<span data-ttu-id="38cde-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="38cde-117">Runtime</span></span>|
