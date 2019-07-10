---
title: Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 114447fd45806e567b4fde8e9e74138c096bff07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743565"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="339e2-102">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="339e2-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="339e2-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per implementare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="339e2-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="339e2-104">In pratica, tuttavia, l'applicazione viene in genere personalizzata per soddisfare specifiche esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="339e2-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="339e2-105">Se si usa Visual Studio, è possibile utilizzare Object Relational Designer per personalizzare l'inserimento, aggiornamento ed eliminazione di azioni.</span><span class="sxs-lookup"><span data-stu-id="339e2-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="339e2-106">Negli argomenti di questa sezione vengono descritte le tecniche offerte da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="339e2-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="339e2-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="339e2-107">In This Section</span></span>  
 [<span data-ttu-id="339e2-108">Personalizzazione di operazioni: panoramica</span><span class="sxs-lookup"><span data-stu-id="339e2-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="339e2-109">Vengono descritte le diverse tecniche fornite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="339e2-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="339e2-110">Operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="339e2-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="339e2-111">Vengono descritti i processi predefiniti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per la modifica dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="339e2-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="339e2-112">Responsabilità dello sviluppatore nell'override del comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="339e2-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="339e2-113">Viene descritto il ruolo dello sviluppatore nell'implementazione dei requisiti non applicati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="339e2-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="339e2-114">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="339e2-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="339e2-115">Viene descritto come usare metodi parziali per eseguire l'override dei metodi generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="339e2-115">Describes how to use partial methods to override autogenerated methods.</span></span>
