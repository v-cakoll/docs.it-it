---
title: Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitori
ms.date: 05/04/2018
ms.openlocfilehash: 54c5945326fb8a50a39c50552a413580926da2c7
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331967"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Scelta delle piattaforme di calcolo di Azure per le applicazioni basate su contenitore

Come si è notato dopo aver letto le sezioni precedenti, Azure è un cloud aperto che offre più opzioni. È tuttavia possibile usare la soluzione più adatta alle proprie esigenze, ma anche le domande sul prodotto/tecnologia da usare per le applicazioni in contenitori.

Come raccomandazione *per impostazione predefinita* , di seguito sono riportati i criteri principali consigliati in questa guida:

- **Singola app monolitica:** Scegliere app Azure servizio
- **App a più livelli:** Scegliere gli agenti di orchestrazione, ad esempio Azure Kubernetes Service (AKS) o il servizio app, se si dispone di un singolo o di pochi servizi back-end
- **Microservizi** Scegliere AKS o app Web di Azure per contenitori
- **Funzioni senza server & gestori eventi:** Scegliere funzioni di Azure
- **Batch su larga scala:** Scegliere Azure Batch

Questa raccomandazione, tuttavia, deve essere eseguita con un pizzico di Salt, in quanto la selezione del prodotto dipende dalle esigenze e dalle caratteristiche specifiche dell'applicazione. Non tutte le applicazioni sono le stesse anche quando inizialmente potrebbero sembrare tipi simili.

Dopo un'analisi più approfondita delle esigenze dell'applicazione, il prodotto selezionato potrebbe essere diverso. Tuttavia, come punto di partenza, è opportuno disporre di indicazioni iniziali da cui è possibile iniziare a valutare e testare in base a una determinata priorità.

Nella figura 1 è possibile visualizzare una suddivisione dei diversi tipi di app e i relativi scenari di hosting di Azure ideali.

![Figura 1](./media/image8.5.png)

> [!div class="step-by-step"]
> [Precedente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Successivo](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
