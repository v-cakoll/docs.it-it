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
# <a name="operating-system-resources-required-by-wcf"></a>Risorse del sistema operativo richieste da WCF

Windows Communication Foundation (WCF) dipende da diverse risorse fornite dal sistema operativo per funzionare. La tabella seguente elenca le risorse seguenti:

|Risorsa|Descrizione|
|--------------|-----------------|
|Microsoft Distributed Transaction Coordinator (MSDTC)|Necessario per supportare le transazioni OleTx.|
|Internet Information Services (IIS)|Necessario se si desidera usare IIS per ospitare l'applicazione.|
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|Necessario se si desidera usare WAS per ospitare l'applicazione.|
