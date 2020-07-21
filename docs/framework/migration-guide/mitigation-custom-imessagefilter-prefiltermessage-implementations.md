---
title: 'Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate'
description: Informazioni sui implementazione personalizzati IMessageFilter. PreFilterMessage inclusi nelle app Windows Forms destinate .NET Framework 4.6.1 e versioni successive.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475255"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="4f943-103">Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate</span><span class="sxs-lookup"><span data-stu-id="4f943-103">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="4f943-104">Nelle app di Windows Forms destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1, un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata può filtrare in modo sicuro i messaggi quando il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> viene chiamato se l'implementazione <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="4f943-104">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="4f943-105">Esegue una o entrambe le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f943-105">Does one or both of the following:</span></span>

  - <span data-ttu-id="4f943-106">Aggiunge un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f943-106">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="4f943-107">Rimuove un filtro messaggio chiamando il metodo <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f943-107">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="4f943-108">ProcessOnStatus.</span><span class="sxs-lookup"><span data-stu-id="4f943-108">method.</span></span>

- <span data-ttu-id="4f943-109">**E** immette i messaggi chiamando il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4f943-109">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="4f943-110">Impatto</span><span class="sxs-lookup"><span data-stu-id="4f943-110">Impact</span></span>

<span data-ttu-id="4f943-111">Questa modifica riguarda solo app Windows Forms destinate a versioni di .NET Framework a partire da .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="4f943-111">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="4f943-112">Per le app Windows Form destinate a versioni precedenti di .NET Framework, questo tipo di implementazioni in alcuni casi genera un'eccezione <xref:System.IndexOutOfRangeException> quando viene chiamato il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4f943-112">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="4f943-113">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="4f943-113">Mitigation</span></span>

<span data-ttu-id="4f943-114">Se questa modifica non è auspicabile, le app destinate a .NET Framework 4.6.1 o una versione successiva possono rifiutare esplicitamente questa modifica aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="4f943-114">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="4f943-115">Inoltre, le app destinate alle versioni precedenti del .NET Framework ma sono in esecuzione nel .NET Framework 4.6.1 o in una versione successiva possono acconsentire esplicitamente a questo comportamento aggiungendo l'impostazione di configurazione seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="4f943-115">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="4f943-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f943-116">See also</span></span>

- [<span data-ttu-id="4f943-117">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="4f943-117">Application compatibility</span></span>](application-compatibility.md)
