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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: aa12b26723c3c97e45f75ae951a7496025fde5a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="92d47-102">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="92d47-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="92d47-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per implementare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="92d47-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="92d47-104">In pratica, tuttavia, l'applicazione viene in genere personalizzata per soddisfare specifiche esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="92d47-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92d47-105">Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile personalizzare le operazioni di inserimento, aggiornamento ed eliminazione tramite [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92d47-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="92d47-106">Negli argomenti di questa sezione vengono descritte le tecniche offerte da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92d47-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92d47-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="92d47-107">In This Section</span></span>  
 [<span data-ttu-id="92d47-108">Personalizzazione di operazioni: panoramica</span><span class="sxs-lookup"><span data-stu-id="92d47-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="92d47-109">Vengono descritte le diverse tecniche fornite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="92d47-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="92d47-110">Operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="92d47-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="92d47-111">Vengono descritti i processi predefiniti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per la modifica dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="92d47-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="92d47-112">Responsabilità dello sviluppatore nell'override del comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="92d47-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="92d47-113">Viene descritto il ruolo dello sviluppatore nell'implementazione dei requisiti non applicati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92d47-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="92d47-114">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="92d47-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="92d47-115">Viene descritto come usare metodi parziali per eseguire l'override dei metodi generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92d47-115">Describes how to use partial methods to override autogenerated methods.</span></span>
