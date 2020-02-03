---
title: Proprietà di accessibilità nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743432"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Proprietà nei controlli Windows Form che supportano le linee guida per l'accesso facilitato
I controlli della casella degli strumenti standard per Windows Forms supportano molte delle linee guida per l'accessibilità, inclusa l'esposizione dello stato attivo della tastiera e l'esposizione degli elementi dello schermo.  
  
## <a name="planning-ahead-for-accessibility"></a>Pianificazione in anticipo per l'accessibilità  
 È possibile utilizzare le proprietà dei controlli per supportare altre linee guida sull'accessibilità, come illustrato nella tabella seguente. Inoltre, è consigliabile utilizzare i menu per fornire l'accesso alle funzionalità del programma.  
  
|Proprietà del controllo|Considerazioni sull'accessibilità|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La descrizione viene segnalata agli strumenti di accessibilità, ad esempio utilità per la lettura dello schermo Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace.|  
|AccessibleName|Nome che verrà segnalato agli strumenti di accessibilità.|  
|AccessibleRole|Viene descritto l'utilizzo dell'elemento nell'interfaccia utente.|  
|TabIndex|Crea un percorso di navigazione sensibile nel form. È importante per i controlli senza etichette intrinseche, ad esempio caselle di testo, per fare in modo che l'etichetta associata venga immediatamente preceduta nell'ordine di tabulazione.|  
|Text|Usare il carattere "&" per creare chiavi di accesso. L'uso delle chiavi di accesso è parte integrante dell'accesso alla tastiera documentato alle funzionalità.|  
|Dimensioni carattere|Se le dimensioni del carattere non sono regolabili, è consigliabile impostarla su un numero di punti pari o superiore a 10. Una volta impostate le dimensioni del carattere del modulo, tutti i controlli aggiunti successivamente al form avranno le stesse dimensioni.|  
|Forecolor|Se questa proprietà è impostata sul valore predefinito, le preferenze di colore dell'utente verranno utilizzate nel form.|  
|Backcolor|Se questa proprietà è impostata sul valore predefinito, le preferenze di colore dell'utente verranno utilizzate nel form.|  
|BackgroundImage|Lasciare vuota questa proprietà per rendere il testo più leggibile.|  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Creazione di un'applicazione Windows ad Accesso facilitato](walkthrough-creating-an-accessible-windows-based-application.md)
