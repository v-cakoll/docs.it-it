---
ms.openlocfilehash: 4fbec1028b6d75b90d4638814c877c263c8c8936
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181983"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="60994-101">TypeDescriptionProviderAttribute spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="60994-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="60994-102">La <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="60994-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="60994-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="60994-103">Change description</span></span>

<span data-ttu-id="60994-104">In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="60994-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="60994-105">A partire da .NET Core 3,0, si trova nell'assembly *System. ObjectModel* .</span><span class="sxs-lookup"><span data-stu-id="60994-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="60994-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="60994-106">Version introduced</span></span>

<span data-ttu-id="60994-107">3.0</span><span class="sxs-lookup"><span data-stu-id="60994-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="60994-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="60994-108">Recommended action</span></span>

<span data-ttu-id="60994-109">Questa modifica riguarda solo le applicazioni che usano la reflection per <xref:System.ComponentModel.TypeDescriptionProviderAttribute> caricare il tipo chiamando un metodo <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> come o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico.</span><span class="sxs-lookup"><span data-stu-id="60994-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="60994-110">In tal caso, l'assembly a cui viene fatto riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="60994-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="60994-111">Category</span><span class="sxs-lookup"><span data-stu-id="60994-111">Category</span></span>

<span data-ttu-id="60994-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="60994-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="60994-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="60994-113">Affected APIs</span></span>

- <span data-ttu-id="60994-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="60994-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->