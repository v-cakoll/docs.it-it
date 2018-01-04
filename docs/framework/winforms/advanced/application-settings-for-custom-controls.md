---
title: Impostazioni delle applicazioni per i controlli personalizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e21a49b26a7493aaec31d5a97e627ce7925f39b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="application-settings-for-custom-controls"></a>Impostazioni delle applicazioni per i controlli personalizzati
È necessario completare alcune attività per consentire ai controlli personalizzati di rendere persistenti le impostazioni dell'applicazione quando sono ospitati i controlli nelle applicazioni di terze parti.  
  
 La maggior parte della documentazione sulla funzionalità Impostazioni applicazione viene scritta presupponendo che si sta creando un'applicazione autonoma. Tuttavia, se si sta creando un controllo che ospitano altri sviluppatori nelle proprie applicazioni, è necessario eseguire alcuni passaggi aggiuntivi per il controllo per la persistenza delle impostazioni in modo corretto.  
  
## <a name="application-settings-and-custom-controls"></a>Le impostazioni dell'applicazione e i controlli personalizzati  
 Per il controllo in modo corretto la persistenza delle impostazioni, è necessario incapsulare il processo tramite la creazione di applicazioni dedicate classe wrapper di impostazioni, derivata da <xref:System.Configuration.ApplicationSettingsBase>. Inoltre, è necessario implementare la classe principale del controllo di <xref:System.Configuration.IPersistComponentSettings>. L'interfaccia contiene diverse proprietà, nonché due metodi, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> e <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Se si aggiunge il controllo a un form utilizzando la **Progettazione Windows Form** in Visual Studio, Windows Form chiamerà <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automaticamente quando il controllo è inizializzato; è necessario chiamare <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> manualmente nel `Dispose` metodo del controllo.  
  
 Inoltre, è opportuno implementare le operazioni seguenti nell'ordine per le impostazioni dell'applicazione per i controlli personalizzati di funzionare correttamente in ambienti di progettazione, ad esempio Visual Studio:  
  
1.  Una classe di impostazioni applicazione personalizzata con un costruttore che accetta un <xref:System.ComponentModel.IComponent> come un singolo parametro. Utilizzare questa classe per salvare e caricare tutte le impostazioni dell'applicazione. Quando si crea una nuova istanza della classe, passare il controllo personalizzato utilizzando il costruttore.  
  
2.  Creare la classe di impostazioni personalizzate dopo il controllo è stato creato e inserito in un form, ad esempio il formato <xref:System.Windows.Forms.Form.Load> gestore dell'evento.  
  
 Per istruzioni sulla creazione di una classe di impostazioni personalizzate, vedere [procedura: creare le impostazioni dell'applicazione](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Le chiavi delle impostazioni e le impostazioni condivise  
 Alcuni controlli possono essere utilizzate più volte nello stesso form. La maggior parte dei casi, si desidererà questi controlli per rendere persistenti le proprie impostazioni. Con il <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> proprietà <xref:System.Configuration.IPersistComponentSettings>, è possibile fornire una stringa univoca che agisce per evitare ambiguità tra più versioni di un controllo in un form.  
  
 Il modo più semplice per implementare <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> consiste nell'utilizzare il <xref:System.Windows.Forms.Control.Name%2A> proprietà del controllo per il <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Quando si caricano o salvano le impostazioni del controllo, si passa il valore di <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> al <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> proprietà del <xref:System.Configuration.ApplicationSettingsBase> classe. Le impostazioni dell'applicazione utilizza questa chiave univoca per rendere persistenti le impostazioni dell'utente in formato XML. Nell'esempio di codice riportato di seguito viene illustrato come un `<userSettings>` sezione potrebbe essere per un'istanza di un controllo personalizzato denominato `CustomControl1` che salva un'impostazione per il relativo `Text` proprietà.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Tutte le istanze di un controllo che non si specifica un valore per <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> condividono le stesse impostazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
