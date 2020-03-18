---
title: Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Informazioni sull'architettura esterna per la progettazione e lo sviluppo di applicazioni .NET basate su più contenitori e microservizi.
ms.date: 10/02/2018
ms.openlocfilehash: 8c2f828e9913a0efcdf580371124b0f624daeffe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70296626"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi

*Lo sviluppo di applicazioni di microservizi containerizzate significa che si stanno creando applicazioni multi-contenitore. Tuttavia, un'applicazione multi-contenitore potrebbe anche essere più semplice, ad esempio un'applicazione a tre livelli, e potrebbe non essere compilata utilizzando un'architettura di microservizio.*

In precedenza ci si è interrogati sulla necessità di Docker per la compilazione di un'architettura di microservizio. In realtà, Docker non è affatto necessario. Docker può rappresentare una chiave di volta e offrire vantaggi significativi, ma i contenitori e Docker non sono un requisito fondamentale per i microservizi. Ad esempio, è possibile creare un'applicazione basata su microservizi con o senza Docker quando si usa Azure Service Fabric, che supporta i microservizi in esecuzione come processi semplici o come contenitori Docker.

Tuttavia, se si sa come progettare e sviluppare un'applicazione basata su microservizi che sia basata anche su contenitori Docker, sarà possibile progettare e sviluppare qualsiasi altro modello di applicazione più semplice. Ad esempio, si potrebbe progettare un'applicazione a tre livelli che richieda anche un approccio a più contenitori. Per questo motivo, e poiché le architetture di microservizi rappresentano una tendenza importante nel mondo dei contenitori, questa sezione è incentrata sull'implementazione di un'architettura di microservizi tramite i contenitori Docker.

>[!div class="step-by-step"]
>[Successivo](../docker-application-development-process/docker-app-development-workflow.md)
>[precedente](microservice-application-design.md)
