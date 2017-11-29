---
title: Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e48ac307087d5b90567c720d0c215ac0d52ccb6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="022e5-102">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="022e5-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="022e5-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per implementare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="022e5-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="022e5-104">In pratica, tuttavia, l'applicazione viene in genere personalizzata per soddisfare specifiche esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="022e5-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="022e5-105">Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile personalizzare le operazioni di inserimento, aggiornamento ed eliminazione tramite [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="022e5-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="022e5-106">Negli argomenti di questa sezione vengono descritte le tecniche offerte da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="022e5-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="022e5-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="022e5-107">In This Section</span></span>  
 [<span data-ttu-id="022e5-108">Personalizzazione di operazioni: Panoramica</span><span class="sxs-lookup"><span data-stu-id="022e5-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="022e5-109">Vengono descritte le diverse tecniche fornite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="022e5-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="022e5-110">Inserimento, aggiornamento e le operazioni di eliminazione</span><span class="sxs-lookup"><span data-stu-id="022e5-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="022e5-111">Vengono descritti i processi predefiniti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per la modifica dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="022e5-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="022e5-112">Responsabilità dello sviluppatore nell'override del comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="022e5-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="022e5-113">Viene descritto il ruolo dello sviluppatore nell'implementazione dei requisiti non applicati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="022e5-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="022e5-114">Aggiunta di logica di Business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="022e5-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="022e5-115">Viene descritto come usare metodi parziali per eseguire l'override dei metodi generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="022e5-115">Describes how to use partial methods to override autogenerated methods.</span></span>
