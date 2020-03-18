---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147536"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="cd30f-101">TypeDescriptionProviderAttribute spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="cd30f-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="cd30f-102">La <xref:System.ComponentModel.TypeDescriptionProviderAttribute> classe è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="cd30f-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cd30f-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="cd30f-103">Change description</span></span>

<span data-ttu-id="cd30f-104">In .NET Core 2.2 e <xref:System.ComponentModel.TypeDescriptionProviderAttribute> versioni precedenti, la classe si trova nell'assembly *System.ComponentModel.TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="cd30f-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="cd30f-105">A partire da .NET Core 3.0, si trova nell'assembly *System.ObjectModel.*</span><span class="sxs-lookup"><span data-stu-id="cd30f-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cd30f-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="cd30f-106">Version introduced</span></span>

<span data-ttu-id="cd30f-107">3.0</span><span class="sxs-lookup"><span data-stu-id="cd30f-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cd30f-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="cd30f-108">Recommended action</span></span>

<span data-ttu-id="cd30f-109">Questa modifica influisce solo sulle applicazioni <xref:System.ComponentModel.TypeDescriptionProviderAttribute> che utilizzano la <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> reflection per <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> caricare il tipo chiamando un metodo, ad esempio o un overload che presuppone che il tipo si trova in un assembly specifico.</span><span class="sxs-lookup"><span data-stu-id="cd30f-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="cd30f-110">In questo caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="cd30f-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="cd30f-111">Category</span><span class="sxs-lookup"><span data-stu-id="cd30f-111">Category</span></span>

<span data-ttu-id="cd30f-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="cd30f-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd30f-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="cd30f-113">Affected APIs</span></span>

<span data-ttu-id="cd30f-114">No.</span><span class="sxs-lookup"><span data-stu-id="cd30f-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
