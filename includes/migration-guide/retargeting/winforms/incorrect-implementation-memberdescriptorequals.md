---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614817"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="527d6-101">Implementazione non corretta di MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="527d6-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="527d6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="527d6-102">Details</span></span>

<span data-ttu-id="527d6-103">L'implementazione originale del metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> confronta due diverse proprietà stringa degli oggetti confrontati: la stringa del nome di categoria e la stringa di descrizione.</span><span class="sxs-lookup"><span data-stu-id="527d6-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="527d6-104">Per risolvere il problema, confrontare <xref:System.ComponentModel.MemberDescriptor.Category> del primo oggetto con <xref:System.ComponentModel.MemberDescriptor.Category> del secondo e <xref:System.ComponentModel.MemberDescriptor.Description> del primo con <xref:System.ComponentModel.MemberDescriptor.Description> del secondo.</span><span class="sxs-lookup"><span data-stu-id="527d6-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="527d6-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="527d6-105">Suggestion</span></span>

<span data-ttu-id="527d6-106">Se l'applicazione dipende dal fatto che <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> talvolta restituisca `false` quando i descrittori sono equivalenti ed è destinata a NET Framework 4.6.2 o versione successiva, sono disponibili varie opzioni:</span><span class="sxs-lookup"><span data-stu-id="527d6-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="527d6-107">Apportare modifiche al codice per confrontare i campi <xref:System.ComponentModel.MemberDescriptor.Category> e <xref:System.ComponentModel.MemberDescriptor.Description> manualmente oltre a chiamare il metodo <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="527d6-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="527d6-108">Rifiutare esplicitamente questa modifica aggiungendo il valore seguente al file app.config:</span><span class="sxs-lookup"><span data-stu-id="527d6-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="527d6-109">Se l'applicazione è destinata a NET Framework 4.6.1 o versioni precedenti ed è in esecuzione in .NET Framework 4.6.2 o versione successiva e si vuole abilitare questa modifica, è possibile impostare l'opzione di compatibilità su `false` aggiungendo il valore seguente al file app.config:</span><span class="sxs-lookup"><span data-stu-id="527d6-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="527d6-110">Nome</span><span class="sxs-lookup"><span data-stu-id="527d6-110">Name</span></span>    | <span data-ttu-id="527d6-111">Valore</span><span class="sxs-lookup"><span data-stu-id="527d6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="527d6-112">Scope</span><span class="sxs-lookup"><span data-stu-id="527d6-112">Scope</span></span>   | <span data-ttu-id="527d6-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="527d6-113">Edge</span></span>        |
| <span data-ttu-id="527d6-114">Version</span><span class="sxs-lookup"><span data-stu-id="527d6-114">Version</span></span> | <span data-ttu-id="527d6-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="527d6-115">4.6.2</span></span>       |
| <span data-ttu-id="527d6-116">Type</span><span class="sxs-lookup"><span data-stu-id="527d6-116">Type</span></span>    | <span data-ttu-id="527d6-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="527d6-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="527d6-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="527d6-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
