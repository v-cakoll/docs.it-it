---
title: Creazione e uso di componenti
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 2fefdff9dc27915066e3d92efd8439adffed9fc5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330303"
---
# <a name="creating-and-using-components-in-visual-basic"></a>Creazione e utilizzo di componenti in Visual Basic

Un *componente* è una classe che implementa l'interfaccia <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> o che deriva direttamente o indirettamente da una classe che implementa <xref:System.ComponentModel.IComponent>. Un componente .NET Framework è un oggetto riutilizzabile, può interagire con altri oggetti e fornisce il controllo sulle risorse esterne e sul supporto della fase di progettazione.  
  
 Una caratteristica importante dei componenti è che possono essere manipolati in fase di progettazione, quindi se una classe è un componente può essere usata nell'ambiente di sviluppo integrato (IDE) di Visual Studio. Un componente può essere aggiunto alla casella degli strumenti, trascinato e rilasciato in un form e manipolato in un'area di progettazione. Si noti che il supporto della fase di progettazione di base per i componenti è integrato nell'.NET Framework; uno sviluppatore di componenti non deve eseguire operazioni aggiuntive per sfruttare la funzionalità di base della fase di progettazione.  
  
 Un *controllo* è simile a un componente, poiché entrambi possono essere manipolati. A differenza di un componente, un controllo produce però un'interfaccia utente. Un controllo deve derivare da una delle classi di controllo di base: <xref:System.Windows.Forms.Control> o <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Quando si crea un componente  

 Se la classe viene usata in un'area di progettazione, ad esempio Windows Form o Progettazione Web Form, ma non ha un'interfaccia utente, deve essere un componente e implementare <xref:System.ComponentModel.IComponent> oppure derivare da una classe che implementa direttamente o indirettamente <xref:System.ComponentModel.IComponent>.  
  
 Le classi <xref:System.ComponentModel.Component> e <xref:System.ComponentModel.MarshalByValueComponent> sono implementazioni di base dell'interfaccia <xref:System.ComponentModel.IComponent>. La differenza principale tra queste classi è che la classe <xref:System.ComponentModel.Component> viene sottoposta a marshalling in base al riferimento, mentre <xref:System.ComponentModel.IComponent> è sottoposta a marshalling in base al valore. L'elenco seguente contiene indicazioni generali per gli implementatori.  
  
- Se il componente deve essere sottoposto a marshalling in base al riferimento, derivare la classe da <xref:System.ComponentModel.Component>.  
  
- Se il componente deve essere sottoposto a marshalling in base al valore, derivare la classe da <xref:System.ComponentModel.MarshalByValueComponent>.  
  
- Se il componente non può derivare da una delle implementazioni di base a causa di un'ereditarietà singola, implementare <xref:System.ComponentModel.IComponent>.  
  
## <a name="component-classes"></a>Classi di componenti  

 Lo spazio dei nomi <xref:System.ComponentModel> offre classi usate per implementare il comportamento dei componenti e dei controlli in fase di progettazione e di esecuzione. Questo spazio dei nomi include le classi e le interfacce di base per l'implementazione di attributi e convertitori, l'associazione a origini dati e le licenze per i componenti.  
  
 Le classi di componenti principali sono:  
  
- <xref:System.ComponentModel.Component>. Un'implementazione di base per l'interfaccia <xref:System.ComponentModel.IComponent>. Questa classe abilita la condivisione degli oggetti tra applicazioni.  
  
- <xref:System.ComponentModel.MarshalByValueComponent>. Un'implementazione di base per l'interfaccia <xref:System.ComponentModel.IComponent>.  
  
- <xref:System.ComponentModel.Container>. L'implementazione di base per l'interfaccia <xref:System.ComponentModel.IContainer>. Questa classe incapsula zero o più componenti.  
  
 Alcune delle classi utilizzate per le licenze dei componenti sono:  
  
- <xref:System.ComponentModel.License>. Classe di base astratta per tutte le licenze. La licenza viene concessa a un'istanza specifica di un componente.  
  
- <xref:System.ComponentModel.LicenseManager>. Offre proprietà e metodi per aggiungere una licenza a un componente e gestire <xref:System.ComponentModel.LicenseProvider>.  
  
- <xref:System.ComponentModel.LicenseProvider>. Classe di base astratta per l'implementazione di un provider di licenza.  
  
- <xref:System.ComponentModel.LicenseProviderAttribute>. Specifica la classe <xref:System.ComponentModel.LicenseProvider> da usare con una classe.  
  
 Classi usate in genere per descrivere e rendere persistenti i componenti.  
  
- <xref:System.ComponentModel.TypeDescriptor>. Offre informazioni sulle caratteristiche di un componente, ad esempio gli attributi, le proprietà e gli eventi.  
  
- <xref:System.ComponentModel.EventDescriptor>. Include informazioni su un evento.  
  
- <xref:System.ComponentModel.PropertyDescriptor>. Include informazioni su una proprietà.  
  
## <a name="related-sections"></a>Sezioni correlate  

 [Risoluzione dei problemi relativi alla modifica di controlli e componenti](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Viene illustrato come risolvere i problemi comuni.  
  
## <a name="see-also"></a>Vedi anche

- [Procedura: Accedere al supporto in fase di progettazione in Windows Forms](../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
