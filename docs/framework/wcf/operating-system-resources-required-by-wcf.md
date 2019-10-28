---
title: Risorse del sistema operativo richieste da WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961141"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="374f1-102">Risorse del sistema operativo richieste da WCF</span><span class="sxs-lookup"><span data-stu-id="374f1-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="374f1-103">Windows Communication Foundation (WCF) dipende da diverse risorse fornite dal sistema operativo per funzionare.</span><span class="sxs-lookup"><span data-stu-id="374f1-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="374f1-104">La tabella seguente elenca le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="374f1-104">The following table lists those resources:</span></span>

|<span data-ttu-id="374f1-105">Risorsa</span><span class="sxs-lookup"><span data-stu-id="374f1-105">Resource</span></span>|<span data-ttu-id="374f1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="374f1-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="374f1-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="374f1-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="374f1-108">Necessario per supportare le transazioni OleTx.</span><span class="sxs-lookup"><span data-stu-id="374f1-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="374f1-109">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="374f1-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="374f1-110">Necessario se si desidera usare IIS per ospitare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="374f1-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="374f1-111">Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="374f1-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="374f1-112">Necessario se si desidera usare WAS per ospitare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="374f1-112">Required if you want to use WAS to host your application.</span></span>|
