---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975350"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="0546b-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="0546b-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="0546b-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="0546b-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0546b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0546b-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0546b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0546b-105">Methods</span></span>  
 <span data-ttu-id="0546b-106">La classe MustUnderstandBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="0546b-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0546b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0546b-107">Properties</span></span>  
 <span data-ttu-id="0546b-108">La classe MustUnderstandBehavior dispone della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="0546b-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="0546b-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="0546b-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="0546b-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="0546b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0546b-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="0546b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0546b-112">Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0546b-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0546b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0546b-113">Requirements</span></span>  
  
|<span data-ttu-id="0546b-114">MOF</span><span class="sxs-lookup"><span data-stu-id="0546b-114">MOF</span></span>|<span data-ttu-id="0546b-115">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0546b-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0546b-116">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="0546b-116">Namespace</span></span>|<span data-ttu-id="0546b-117">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0546b-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0546b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0546b-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
