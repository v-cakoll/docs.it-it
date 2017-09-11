---
title: Sezione di configurazione di Windows Form | Microsoft Docs
ms.custom: 
ms.date: 04/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: dedf9497a684c4b11f84b60de21ec73b563c6d19
ms.contentlocale: it-it
ms.lasthandoff: 05/03/2017

---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="b282b-102">Sezione di configurazione di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b282b-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="b282b-103">Le impostazioni di configurazione di Windows Form consentono a un'app Windows Form di archiviare e recuperare informazioni sulle impostazioni dell'applicazione personalizzate, ad esempio il supporto di più monitor, il supporto di valori DPI alti e altre impostazioni di configurazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="b282b-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="b282b-104">Le impostazioni di configurazione dell'applicazione Windows Form sono archiviate in un elemento `System.Windows.Forms.ConfigurationSection` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b282b-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="b282b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b282b-105">Syntax</span></span>

```xml
<configuration>
  \<System.Windows.Forms.ConfigurationSection>
  ...
  \</System.Windows.Forms.ConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b282b-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b282b-106">Attributes and elements</span></span>

<span data-ttu-id="b282b-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b282b-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b282b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b282b-108">Attributes</span></span>

<span data-ttu-id="b282b-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b282b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b282b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b282b-110">Child elements</span></span>

<span data-ttu-id="b282b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b282b-111">Element</span></span>  |<span data-ttu-id="b282b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b282b-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="b282b-113">Aggiunge una chiave per l'impostazione di configurazione con un valore specificato</span><span class="sxs-lookup"><span data-stu-id="b282b-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b282b-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b282b-114">Parent elements</span></span>

<span data-ttu-id="b282b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b282b-115">Element</span></span>  |<span data-ttu-id="b282b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b282b-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="b282b-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b282b-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="b282b-118">Elemento radice in ogni file di configurazione usato in Common Language Runtime e nelle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="b282b-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="b282b-119">Note</span><span class="sxs-lookup"><span data-stu-id="b282b-119">Remarks</span></span>

<span data-ttu-id="b282b-120">A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b282b-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="b282b-121">L'elemento `<System.Windows.Forms.ConfigurationSection>` può includere uno o più elementi [ `<add>` ](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) figlio, ognuno dei quali definisce un'impostazione di configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="b282b-121">The `<System.Windows.Forms.ConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="b282b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b282b-122">See also</span></span>

<span data-ttu-id="b282b-123">[Schema del file di configurazione](../index.md)
[Supporto di valori DPI alti in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b282b-123">[Configuration File Schema](../index.md)
[High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)</span></span>

