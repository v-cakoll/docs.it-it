---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0ce7c66946d03d566b21473711cb6b3315885236
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61952048"
---
# <a name="multiple-document-interface-mdi-applications"></a>Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
Le applicazioni di interfaccia a documenti multipli (MDI) consentono di visualizzare documenti multipli nello stesso momento, con ogni documento visualizzato in una finestra. Le applicazioni MDI hanno spesso una voce di menu finestra con sottomenu per lo spostamento tra finestre e documenti.  
  
> [!NOTE]
>  Esistono alcune differenze di comportamento tra i form MDI e interfaccia a documento singolo (SDI) windows in Windows Form. Il `Opacity` proprietà non influiscono sull'aspetto del form figlio MDI. Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> (metodo) non influiscono sul comportamento dei form figlio MDI.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)  
 Fornisce indicazioni per la creazione del contenitore per più documenti all'interno di un'applicazione MDI.  
  
 [Procedura: Creare form figlio MDI](how-to-create-mdi-child-forms.md)  
 Vengono fornite indicazioni per la creazione di una o più finestre usate all'interno di un form padre MDI.  
  
 [Procedura: Determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)  
 Fornisce indicazioni per la verifica per determinare se la finestra figlio con lo stato attivo (e invia il contenuto negli Appunti).  
  
 [Procedura: Inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)  
 Fornisce indicazioni per il trasferimento delle informazioni alla finestra figlio attiva.  
  
 [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)  
 Vengono fornite indicazioni per l'affiancamento, CSS o disporre le finestre figlio di un'applicazione MDI.
