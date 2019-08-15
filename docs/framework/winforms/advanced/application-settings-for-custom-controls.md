---
title: Impostazioni delle applicazioni per i controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040467"
---
# <a name="application-settings-for-custom-controls"></a>Impostazioni delle applicazioni per i controlli personalizzati
È necessario completare determinate attività per offrire ai controlli personalizzati la possibilità di rendere permanente le impostazioni dell'applicazione quando i controlli sono ospitati in applicazioni di terze parti.

 La maggior parte della documentazione relativa alla funzionalità Impostazioni applicazione viene scritta secondo il presupposto che si stia creando un'applicazione autonoma. Tuttavia, se si crea un controllo che altri sviluppatori ospiteranno nelle proprie applicazioni, è necessario eseguire alcuni passaggi aggiuntivi affinché il controllo renda le impostazioni in modo permanente.

## <a name="application-settings-and-custom-controls"></a>Impostazioni dell'applicazione e controlli personalizzati
 Affinché il controllo mantenesse correttamente le impostazioni, deve incapsulare il processo creando la relativa classe wrapper di impostazioni applicazioni dedicate <xref:System.Configuration.ApplicationSettingsBase>, derivata da. Inoltre, la classe del controllo principale deve implementare <xref:System.Configuration.IPersistComponentSettings>. L'interfaccia contiene diverse proprietà, oltre a due metodi, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> e <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>. Se si aggiunge il controllo a un form usando il **Progettazione Windows Form** in Visual Studio, Windows Forms <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> chiamerà automaticamente quando il controllo viene inizializzato. è necessario `Dispose` chiamare <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> manualmente nel metodo del controllo.

 Inoltre, è necessario implementare quanto segue per consentire il corretto funzionamento delle impostazioni dell'applicazione per i controlli personalizzati in ambienti della fase di progettazione, ad esempio Visual Studio:

1. Classe di impostazioni dell'applicazione personalizzata con un costruttore che accetta <xref:System.ComponentModel.IComponent> un oggetto come parametro singolo. Usare questa classe per salvare e caricare tutte le impostazioni dell'applicazione. Quando si crea una nuova istanza di questa classe, passare il controllo personalizzato tramite il costruttore.

2. Creare questa classe di impostazioni personalizzate dopo che il controllo è stato creato e inserito in un modulo, ad esempio nel gestore <xref:System.Windows.Forms.Form.Load> eventi del modulo.

 Per istruzioni sulla creazione di una classe di impostazioni personalizzata [, vedere Procedura: Creare le impostazioni](how-to-create-application-settings.md)dell'applicazione.

## <a name="settings-keys-and-shared-settings"></a>Impostazioni chiavi e impostazioni condivise
 Alcuni controlli possono essere usati più volte nello stesso formato. Nella maggior parte dei casi, è opportuno che questi controlli mantengono le proprie impostazioni personali. Con la <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> proprietà su <xref:System.Configuration.IPersistComponentSettings>, è possibile fornire una stringa univoca che agisce per evitare ambiguità tra più versioni di un controllo in un form.

 Il modo più semplice per implementare <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> consiste nell'usare la <xref:System.Windows.Forms.Control.Name%2A> proprietà <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>del controllo per. Quando si caricano o si salvano le impostazioni del controllo, il valore <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> di viene passato <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> alla proprietà della <xref:System.Configuration.ApplicationSettingsBase> classe. Le impostazioni dell'applicazione usano questa chiave univoca quando le impostazioni dell'utente vengono rese permanente in formato XML. Nell'esempio di codice seguente viene illustrato `<userSettings>` come una sezione può cercare un'istanza di un controllo personalizzato `CustomControl1` denominato che salva un'impostazione per `Text` la relativa proprietà.

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 Tutte le istanze di un controllo che non forniscono un valore per <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> condivideranno le stesse impostazioni.

## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [Application Settings Architecture](application-settings-architecture.md)
