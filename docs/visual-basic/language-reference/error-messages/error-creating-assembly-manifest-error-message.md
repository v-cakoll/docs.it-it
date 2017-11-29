---
title: 'Errore durante la creazione di manifesto dell''assembly: &lt;messaggio di errore&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Errore durante la creazione di manifesto dell'assembly: &lt;messaggio di errore&gt;
Il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto. Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.  
  
 Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato. Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata. Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica. Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria. Per ulteriori informazioni, vedere [procedura: firmare un Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **ID errore:** BC30140  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare il messaggio di errore tra virgolette e consultare l'argomento [Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) per correggere l'errore AL1019 ulteriori spiegazioni e consigli  
  
2.  Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: firmare un assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [Pagina Firma, Creazione progetti](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex)  
 [Lo strumento Al.exe errori e avvisi](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [Comunicazioni con Microsoft](/visualstudio/ide/talk-to-us)
