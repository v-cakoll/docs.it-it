---
title: Estensione del sistema di metadati
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795716"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="d18eb-102">Estensione del sistema di metadati</span><span class="sxs-lookup"><span data-stu-id="d18eb-102">Extending the Metadata System</span></span>
<span data-ttu-id="d18eb-103">Il sistema di metadati Windows Communication Foundation (WCF) è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate su servizi.</span><span class="sxs-lookup"><span data-stu-id="d18eb-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="d18eb-104">Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d18eb-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d18eb-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d18eb-105">In This Section</span></span>  
 [<span data-ttu-id="d18eb-106">Esportazione di metadati personalizzati per un'estensione WCF</span><span class="sxs-lookup"><span data-stu-id="d18eb-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="d18eb-107">Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> per incorporare asserzioni di criteri personalizzate nei documenti WSDL.</span><span class="sxs-lookup"><span data-stu-id="d18eb-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="d18eb-108">Importazione di metadati personalizzati per un'estensione WCF</span><span class="sxs-lookup"><span data-stu-id="d18eb-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="d18eb-109">Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> per leggere e rispondere ad asserzioni di criteri personalizzate in documenti WSDL.</span><span class="sxs-lookup"><span data-stu-id="d18eb-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="d18eb-110">Pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="d18eb-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="d18eb-111">Viene descritto come scambiare metadati su associazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d18eb-111">Describes how to exchange metadata over custom bindings.</span></span>
