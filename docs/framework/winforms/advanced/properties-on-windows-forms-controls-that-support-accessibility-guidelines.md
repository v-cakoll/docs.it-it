---
title: Proprietà nei controlli Windows Form che supportano le linee guida per l'accesso facilitato
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b3f10fe472e449d39385facdbc716cba9b3f7382
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640495"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Proprietà nei controlli Windows Form che supportano le linee guida per l'accesso facilitato
Controlli della casella degli strumenti standard per i moduli di Windows supportano molte delle linee guida accessibilità, inclusi che espone lo stato attivo e l'esposizione degli elementi dello schermo.  
  
## <a name="planning-ahead-for-accessibility"></a>La pianificazione per l'accessibilità  
 Le proprietà dei controlli sono utilizzabile per supportare altre linee guida sull'accessibilità, come illustrato nella tabella seguente. Inoltre, è consigliabile usare i menu per fornire accesso alle funzionalità del programma.  
  
|Proprietà del controllo|Considerazioni per l'accessibilità|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La descrizione viene segnalata agli strumenti di accessibilità, ad esempio lettori dello schermo. Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace.|  
|AccessibleName|Il nome che verrà segnalato agli strumenti di accessibilità.|  
|AccessibleRole|Viene descritto l'utilizzo dell'elemento nell'interfaccia utente.|  
|TabIndex|Crea un percorso di navigazione sensibile attraverso il form. È importante per i controlli senza le etichette intrinseche, ad esempio caselle di testo, per disporre le etichette associate immediatamente li precedono nell'ordine di tabulazione.|  
|Testo|Usare il carattere "&" per creare le chiavi di accesso. Usando le chiavi di accesso fa parte di accesso da tastiera documentato a funzionalità.|  
|Dimensione carattere|Se le dimensioni del carattere non sono modificabile, quindi deve essere impostato a 10 punti o superiori. Dopo aver impostata le dimensioni del form del tipo di carattere, tutti i controlli aggiunti in seguito al form avranno le stesse dimensioni.|  
|Forecolor|Se questa proprietà è impostata sul valore predefinito, le preferenze dell'utente colore verranno usate nel form.|  
|Backcolor|Se questa proprietà è impostata sul valore predefinito, le preferenze dell'utente colore verranno usate nel form.|  
|BackgroundImage|Omettere questa proprietà per rendere più leggibile il testo.|  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Creazione di un'applicazione basata su Windows accessibile](walkthrough-creating-an-accessible-windows-based-application.md)
