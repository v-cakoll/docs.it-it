---
title: "Errore durante la creazione manifesto dell'assembly: <error message>"
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 0f67b772bab3104c00510954d01b200aadfa9e8a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296290"
---
# <a name="error-creating-assembly-manifest-error-message"></a>Errore durante la creazione di manifesto dell'assembly: \<messaggio di errore >
Il compilatore Visual Basic chiama Assembly Linker (Al.exe, definito anche Alink) per generare un assembly con un manifesto. Il linker ha segnalato un errore nella fase di pre-emissione della creazione dell'assembly.  
  
 Questo può accadere se si verificano errori con il file di chiave o il contenitore di chiavi specificato. Per la firma completa di un assembly, è necessario fornire un file di chiave valido contenente informazioni sulle chiavi pubblica e privata. Per ritardare la firma di un assembly, è necessario selezionare la casella di controllo **Solo firma ritardata** e fornire un file di chiave valido contenente informazioni sulla chiave pubblica. Quando la firma di un assembly viene ritardata, la chiave privata non è necessaria. Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **ID errore:** BC30140  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Esaminare il messaggio di errore riportato e vedere l'argomento [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Per ulteriori errore AL1019 spiegazioni e suggerimenti  
  
2. Se l'errore persiste, raccogliere informazioni sulla situazione contingente e informare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Firmare un assembly con un nome sicuro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [Pagina Firma, Progettazione progetti](/visualstudio/ide/reference/signing-page-project-designer)
- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Talk to Us](/visualstudio/ide/talk-to-us)
