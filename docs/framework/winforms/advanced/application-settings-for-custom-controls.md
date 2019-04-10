---
title: Impostazioni delle applicazioni per i controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: 69a5caef8bab45503b9f34422de8c2ba2e7f01ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317298"
---
# <a name="application-settings-for-custom-controls"></a>Impostazioni delle applicazioni per i controlli personalizzati
È necessario completare alcune attività per consentire ai controlli personalizzati la possibilità di mantenere le impostazioni dell'applicazione quando i controlli sono ospitati nelle applicazioni di terze parti.  
  
 La maggior parte della documentazione sulla funzionalità Impostazioni applicazione viene scritta in base al presupposto che si sta creando un'applicazione autonoma. Tuttavia, se si sta creando un controllo che altri sviluppatori ospiterà nelle proprie applicazioni, è necessario eseguire alcuni passaggi aggiuntivi per il controllo per la persistenza delle impostazioni in modo corretto.  
  
## <a name="application-settings-and-custom-controls"></a>Le impostazioni dell'applicazione e i controlli personalizzati  
 Per il controllo in modo corretto la persistenza delle impostazioni, è necessario incapsulare il processo mediante la creazione di una proprio applicazioni dedicate classe wrapper delle impostazioni, derivata da <xref:System.Configuration.ApplicationSettingsBase>. Inoltre, la classe di controllo principale deve implementare il <xref:System.Configuration.IPersistComponentSettings>. L'interfaccia contiene diverse proprietà, nonché due metodi, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> e <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Se si aggiunge il controllo a un form utilizzando la **finestra di progettazione Windows Form** in Visual Studio, verrà chiamata Windows Form <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automaticamente quando il controllo è inizializzato; è necessario chiamare <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> autonomamente nel `Dispose` metodo del controllo.  
  
 Inoltre, è necessario implementare quanto segue in ordine per le impostazioni dell'applicazione per i controlli personalizzati per il corretto funzionamento in fase di progettazione di ambienti, ad esempio Visual Studio:  
  
1. Una classe di impostazioni dell'applicazione personalizzata con un costruttore che accetta un <xref:System.ComponentModel.IComponent> come un singolo parametro. Utilizzare questa classe per salvare e caricare tutte le impostazioni dell'applicazione. Quando si crea una nuova istanza di questa classe, passare il controllo personalizzato usando il costruttore.  
  
2. Creare questa classe di impostazioni personalizzati dopo il controllo è stato creato e inserito in un form, ad esempio il modulo <xref:System.Windows.Forms.Form.Load> gestore dell'evento.  
  
 Per istruzioni sulla creazione di una classe di impostazioni personalizzate, vedere [come: Creare le impostazioni dell'applicazione](how-to-create-application-settings.md).  
  
## <a name="settings-keys-and-shared-settings"></a>Le chiavi delle impostazioni e le impostazioni condivise  
 Alcuni controlli possono essere utilizzati più volte all'interno del modulo stesso. La maggior parte dei casi, è consigliabile questi controlli per rendere persistenti le proprie impostazioni. Con il <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> proprietà <xref:System.Configuration.IPersistComponentSettings>, è possibile fornire una stringa univoca che agisce per evitare ambiguità tra più versioni di un controllo in un form.  
  
 Il modo più semplice per implementare <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> consiste nell'usare il <xref:System.Windows.Forms.Control.Name%2A> proprietà del controllo per il <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>. Quando si caricano o si salvano le impostazioni del controllo, si passa il valore della <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> alla <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> proprietà del <xref:System.Configuration.ApplicationSettingsBase> classe. Le impostazioni dell'applicazione usa questa chiave univoca per rendere persistenti le impostazioni dell'utente in formato XML. Il codice seguente esempio viene illustrato come un `<userSettings>` sezione può avere un aspetto di un'istanza di un controllo personalizzato denominato `CustomControl1` che consente di salvare un'impostazione per relativo `Text` proprietà.  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 Tutte le istanze di un controllo che non si specifica un valore per <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> condivideranno le stesse impostazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Architettura Impostazioni applicazione](application-settings-architecture.md)
