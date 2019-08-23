---
title: Elemento <assemblyBinding> per <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921267"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="deb5d-102">\<assembly > elemento per la \<configurazione ></span><span class="sxs-lookup"><span data-stu-id="deb5d-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="deb5d-103">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="deb5d-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="deb5d-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="deb5d-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="deb5d-105">&nbsp;&nbsp; **\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="deb5d-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="deb5d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="deb5d-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="deb5d-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="deb5d-107">Attribute</span></span>

|           | <span data-ttu-id="deb5d-108">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="deb5d-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="deb5d-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="deb5d-109">**xmlns**</span></span> | <span data-ttu-id="deb5d-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="deb5d-110">Required attribute.</span></span><br><br><span data-ttu-id="deb5d-111">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="deb5d-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="deb5d-112">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="deb5d-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="deb5d-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="deb5d-113">Parent element</span></span>

|     | <span data-ttu-id="deb5d-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="deb5d-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="deb5d-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="deb5d-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="deb5d-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="deb5d-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="deb5d-117">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="deb5d-117">Child element</span></span>

|     | <span data-ttu-id="deb5d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="deb5d-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="deb5d-119"> **\<linkedConfiguration>** </span><span class="sxs-lookup"><span data-stu-id="deb5d-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="deb5d-120">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="deb5d-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="deb5d-121">Note</span><span class="sxs-lookup"><span data-stu-id="deb5d-121">Remarks</span></span>

<span data-ttu-id="deb5d-122">L'elemento > linkedConfiguration semplifica la gestione degli assembly dei componenti consentendo ai file di configurazione dell'applicazione di includere i file di configurazione degli assembly in posizioni note, anziché duplicare l'assembly [ **\<** ](linkedconfiguration-element.md) impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="deb5d-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="deb5d-123">L'elemento > linkedConfiguration non è supportato per le applicazioni con manifesti affiancati di Windows.  **\<**</span><span class="sxs-lookup"><span data-stu-id="deb5d-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="deb5d-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="deb5d-124">Example</span></span>

<span data-ttu-id="deb5d-125">Nell'esempio seguente viene illustrato come includere un file di configurazione nel disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="deb5d-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="deb5d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deb5d-126">See also</span></span>

- [<span data-ttu-id="deb5d-127">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="deb5d-127">Configuration file schema for the .NET Framework</span></span>](index.md)
