---
title: 'Personalizzazione di operazioni: Panoramica'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 48116887471709c60c9666f68c7ebdd0e6d128a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247521"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="54ca3-102">Personalizzazione di operazioni: Panoramica</span><span class="sxs-lookup"><span data-stu-id="54ca3-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="54ca3-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per le operazioni di inserimento, aggiornamento ed eliminazione basate su mapping.</span><span class="sxs-lookup"><span data-stu-id="54ca3-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="54ca3-104">In pratica, tuttavia, la logica di business viene generalmente aggiunta per fornire sicurezza, convalida e così via.</span><span class="sxs-lookup"><span data-stu-id="54ca3-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="54ca3-105">di seguito sono riportate le tecniche per la personalizzazione di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="54ca3-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="54ca3-106">Caricamento di opzioni</span><span class="sxs-lookup"><span data-stu-id="54ca3-106">Loading Options</span></span>  
 <span data-ttu-id="54ca3-107">Nelle query è possibile controllare la quantità di dati relativi alla destinazione principale recuperata durante la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="54ca3-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="54ca3-108">Questa funzionalità viene ampiamente implementata usando <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="54ca3-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="54ca3-109">Per ulteriori informazioni, vedere il [caricamento posticipato rispetto al caricamento immediato](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="54ca3-109">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="54ca3-110">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="54ca3-110">Partial Methods</span></span>  
 <span data-ttu-id="54ca3-111">Nel mapping predefinito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono forniti metodi parziali per facilitare l'implementazione della logica di business.</span><span class="sxs-lookup"><span data-stu-id="54ca3-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="54ca3-112">Per ulteriori informazioni, vedere [aggiunta di logica di business utilizzando metodi parziali](adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="54ca3-112">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="54ca3-113">Stored procedure e funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="54ca3-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="54ca3-114">supporta l'utilizzo di stored procedure e funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="54ca3-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="54ca3-115">Le stored procedure vengono solitamente usate per personalizzare operazioni.</span><span class="sxs-lookup"><span data-stu-id="54ca3-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="54ca3-116">Per altre informazioni, vedere [Stored procedure](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="54ca3-116">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ca3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54ca3-117">See also</span></span>

- [<span data-ttu-id="54ca3-118">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="54ca3-118">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
