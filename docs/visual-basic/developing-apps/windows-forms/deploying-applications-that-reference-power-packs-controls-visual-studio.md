---
title: Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d73c7111c3d89cadcad317c9a67e5f483da7125
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Distribuzione di applicazioni che fanno riferimento a controlli Power Pack (Visual Studio)
Se si desidera distribuire un'applicazione che fa riferimento ai controlli Power Pack (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), i controlli devono essere installati nel computer di destinazione.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Installazione dei controlli Power Pack come prerequisito  
 Per distribuire correttamente un'applicazione, è necessario distribuire anche tutti i componenti a cui viene fatto riferimento dall'applicazione. Il processo di installazione dei componenti prerequisiti è noto come *bootstrap*.  
  
 Quando Visual Studio è installato nel computer di sviluppo, un pacchetto bootstrapper Power viene aggiunto alla directory del programma di avvio automatico di Visual Studio. Questo pacchetto sarà quindi disponibile quando si eseguono le procedure per l'aggiunta dei prerequisiti per la distribuzione tramite [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.  
  
 Per impostazione predefinita, i componenti con bootstrap vengono distribuiti dallo stesso percorso del pacchetto di installazione. In alternativa, è possibile scegliere di distribuire i componenti da un URL o un percorso di condivisione file, da cui gli utenti possono scaricarli in base alle esigenze.  
  
> [!NOTE]
>  Per installare i componenti con bootstrap, l'utente può richiedere autorizzazioni amministrative o di tipo simile per il computer. Per le applicazioni [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , questo significa che l'utente dovrà disporre di autorizzazioni amministrative per installare l'applicazione, indipendentemente dal livello di sicurezza specificato dall'applicazione. Dopo l'installazione dell'applicazione, l'utente può eseguire l'applicazione senza autorizzazioni amministrative.  
  
 Durante l'installazione, agli utenti verranno richiesto di installare i controlli Power Pack se non sono presenti nel computer di destinazione.  
  
 In alternativa al bootstrap, è possibile pre-distribuire i controlli Power Pack utilizzando un sistema di distribuzione software elettronico, ad esempio Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Installare i prerequisiti con un'applicazione ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Controlli Visual Basic Power Pack](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
