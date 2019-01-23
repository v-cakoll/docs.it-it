---
title: Distribuzione di applicazioni che fanno riferimento al componente PrintForm (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
ms.openlocfilehash: 78d332c88b45fa9b1204d9d5352a6027409254e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562427"
---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>Distribuzione di applicazioni che fanno riferimento al componente PrintForm (Visual Basic)
Se si vuole distribuire un'applicazione che fa riferimento al componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , il componente deve essere installato nel computer di destinazione.  
  
 I controlli PowerPacks non sono più inclusi in Visual Studio, ma è possibile scaricarli dall' [Area download](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>Installazione di PrintForm come prerequisito  
 Per distribuire correttamente un'applicazione, è necessario distribuire anche tutti i componenti a cui viene fatto riferimento dall'applicazione. Il processo di installazione dei componenti prerequisiti è noto come *bootstrap*.  
  
 Quando il <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> componente è installato nel computer di sviluppo, un pacchetto bootstrapper di Microsoft Visual Basic Power Packs viene aggiunto alla directory del programma di bootstrap di Visual Studio. Questo pacchetto sarà quindi disponibile quando si eseguono le procedure per l'aggiunta dei prerequisiti per la distribuzione tramite [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] o Windows Installer.  
  
 Per impostazione predefinita, i componenti con bootstrap vengono distribuiti dallo stesso percorso del pacchetto di installazione. In alternativa, è possibile scegliere di distribuire i componenti da un URL o un percorso di condivisione file, da cui gli utenti possono scaricarli in base alle esigenze.  
  
> [!NOTE]
>  Per installare i componenti con bootstrap, l'utente può richiedere autorizzazioni amministrative o di tipo simile per il computer. Per le applicazioni [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] , questo significa che l'utente dovrà disporre di autorizzazioni amministrative per installare l'applicazione, indipendentemente dal livello di sicurezza specificato dall'applicazione. Dopo l'installazione dell'applicazione, l'utente può eseguire l'applicazione senza autorizzazioni amministrative.  
  
 Durante l'installazione, verrà richiesto agli utenti di installare il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> , se non è presente nel computer di destinazione.  
  
 In alternativa al bootstrap, è possibile pre-distribuire il componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> mediante un sistema elettronico di distribuzione del software come Microsoft Systems Management Server.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Installare i prerequisiti con un'applicazione ClickOnce](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)
- [Componente PrintForm](../../../visual-basic/developing-apps/printing/printform-component.md)
