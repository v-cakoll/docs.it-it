---
title: 'Personalizzazione di operazioni: panoramica'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9776daa28b0a7ffcd3b721f004f5b9a44dd09f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="57c22-102">Personalizzazione di operazioni: panoramica</span><span class="sxs-lookup"><span data-stu-id="57c22-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="57c22-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per le operazioni di inserimento, aggiornamento ed eliminazione basate su mapping.</span><span class="sxs-lookup"><span data-stu-id="57c22-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="57c22-104">In pratica, tuttavia, la logica di business viene generalmente aggiunta per fornire sicurezza, convalida e così via.</span><span class="sxs-lookup"><span data-stu-id="57c22-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="57c22-105">di seguito sono illustrate le tecniche di personalizzazione di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="57c22-105"> techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="57c22-106">Caricamento di opzioni</span><span class="sxs-lookup"><span data-stu-id="57c22-106">Loading Options</span></span>  
 <span data-ttu-id="57c22-107">Nelle query è possibile controllare la quantità di dati relativi alla destinazione principale recuperata durante la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="57c22-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="57c22-108">Questa funzionalità viene ampiamente implementata usando <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="57c22-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="57c22-109">Per ulteriori informazioni, vedere [posticipata e il caricamento immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="57c22-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="57c22-110">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="57c22-110">Partial Methods</span></span>  
 <span data-ttu-id="57c22-111">Nel mapping predefinito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono forniti metodi parziali per facilitare l'implementazione della logica di business.</span><span class="sxs-lookup"><span data-stu-id="57c22-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="57c22-112">Per ulteriori informazioni, vedere [aggiunta Business logica da utilizzando i metodi parziali](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="57c22-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="57c22-113">Stored procedure e funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="57c22-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="57c22-114">supporta l'utilizzo di stored procedure e funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="57c22-114"> supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="57c22-115">Le stored procedure vengono solitamente usate per personalizzare operazioni.</span><span class="sxs-lookup"><span data-stu-id="57c22-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="57c22-116">Per altre informazioni, vedere [Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="57c22-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c22-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c22-117">See Also</span></span>  
 [<span data-ttu-id="57c22-118">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="57c22-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
