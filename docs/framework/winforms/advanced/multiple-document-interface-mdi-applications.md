---
title: Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
description: Informazioni su come Windows Forms le applicazioni con interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti contemporaneamente, con ogni documento visualizzato in una finestra.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174653"
---
# <a name="multiple-document-interface-mdi-applications"></a>Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)
Le applicazioni con interfaccia a documenti multipli (MDI) consentono di visualizzare più documenti contemporaneamente, con ogni documento visualizzato in una finestra. Le applicazioni MDI spesso dispongono di una voce di menu finestra con sottomenu per passare da una finestra all'altra o da documenti.  
  
> [!NOTE]
> Esistono alcune differenze di comportamento tra i form MDI e le finestre di interfaccia a documento singolo (SDI) in Windows Forms. La `Opacity` proprietà non influisce sull'aspetto dei form figlio MDI. Inoltre, il <xref:System.Windows.Forms.Form.CenterToParent%2A> metodo non influisce sul comportamento dei form figlio MDI.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)  
 Fornisce indicazioni per la creazione del contenitore per più documenti all'interno di un'applicazione MDI.  
  
 [Procedura: creare form figlio MDI](how-to-create-mdi-child-forms.md)  
 Fornisce indicazioni per la creazione di una o più finestre che operano all'interno di un form padre MDI.  
  
 [Procedura: determinare il figlio MDI attivo](how-to-determine-the-active-mdi-child.md)  
 Fornisce indicazioni per verificare la finestra figlio con lo stato attivo (e inviarne il contenuto agli Appunti).  
  
 [Procedura: inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)  
 Fornisce indicazioni per il trasporto delle informazioni nella finestra figlio attiva.  
  
 [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)  
 Fornisce indicazioni per l'affiancamento, la propagazione o la disposizione delle finestre figlio di un'applicazione MDI.
