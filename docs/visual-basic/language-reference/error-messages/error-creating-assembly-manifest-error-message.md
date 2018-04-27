---
title: "Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4032bbcbf9924eb5aad4e2cb1a6e74df9a472eca
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;
Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto. Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.  
  
 Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato. Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata. Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica. Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria. Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **ID errore:** BC30140  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Per correggere l'errore AL1019 ulteriori spiegazioni e consigli  
  
2.  Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Pagina Firma, Creazione progetti](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
