---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 334bab97a04ed464dce6944692b04a9ed1295296
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613824"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="1e01a-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="1e01a-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="1e01a-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="1e01a-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e01a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e01a-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1e01a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1e01a-105">Methods</span></span>  
 <span data-ttu-id="1e01a-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="1e01a-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1e01a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1e01a-107">Properties</span></span>  
 <span data-ttu-id="1e01a-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="1e01a-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="1e01a-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="1e01a-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="1e01a-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="1e01a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e01a-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="1e01a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e01a-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1e01a-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e01a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e01a-113">Requirements</span></span>  
  
|<span data-ttu-id="1e01a-114">MOF</span><span class="sxs-lookup"><span data-stu-id="1e01a-114">MOF</span></span>|<span data-ttu-id="1e01a-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1e01a-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1e01a-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1e01a-116">Namespace</span></span>|<span data-ttu-id="1e01a-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e01a-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e01a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e01a-118">See also</span></span>
- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
