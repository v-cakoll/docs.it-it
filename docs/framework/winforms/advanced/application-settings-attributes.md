---
title: Attributi delle impostazioni delle applicazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4255356d4e50f3e8be28024f29701e0e9c010473
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="application-settings-attributes"></a>Attributi delle impostazioni delle applicazioni
L'architettura Impostazioni applicazione fornisce numerosi attributi che è possono applicare la classe wrapper di impostazioni o alle singole proprietà. Questi attributi vengono esaminati in fase di esecuzione dall'infrastruttura di impostazioni applicazione, spesso in modo specifico il provider di impostazioni, per personalizzare il funzionamento alle esigenze dichiarate del wrapper personalizzato.  
  
 Nella tabella seguente elenca gli attributi che possono essere applicati per la classe wrapper di impostazioni applicazione, le singole proprietà della classe o entrambi. Per definizione, solo un attributo singolo ambito, ovvero**UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**, deve essere applicato a tutte le proprietà delle impostazioni.  
  
> [!NOTE]
>  Un provider di impostazioni personalizzato, derivato dal <xref:System.Configuration.SettingsProvider> classe, è necessario solo per riconoscere i seguenti tre attributi: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, e **DefaultSettingValueAttribute**.  
  
|Attributo|destinazione|Descrizione|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Entrambi|Specifica il nome breve del provider di impostazioni da utilizzare per la persistenza.<br /><br /> Se questo attributo viene omesso, il provider predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, verrà utilizzato.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Entrambi|Definisce una proprietà come un'impostazione con ambito di utente dell'applicazione.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Entrambi|Definisce una proprietà come un'impostazione con ambito di applicazione dell'applicazione.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Proprietà|Specifica una stringa che può essere deserializzata dal provider, il valore predefinito a livello di codice per questa proprietà.<br /><br /> Il <xref:System.Configuration.LocalFileSettingsProvider> non richiede questo attributo e ignorerà qualsiasi valore fornito da questo attributo se esiste già un valore persistente.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Proprietà|Fornisce il testo descrittivo per una singola impostazione, usata principalmente dagli strumenti in fase di esecuzione e in fase di progettazione.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Classe|Fornisce un nome esplicito per un gruppo di impostazioni. Se questo attributo è manca, <xref:System.Configuration.ApplicationSettingsBase> utilizza il nome della classe wrapper.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Classe|Fornisce il testo descrittivo per un gruppo di impostazioni, usato principalmente dagli strumenti in fase di esecuzione e in fase di progettazione.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Entrambi|Specifica zero o più servizi di gestibilità che devono essere forniti per gruppo di impostazioni o proprietà. I servizi disponibili sono indicati il <xref:System.Configuration.SettingsManageability> enumerazione.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Proprietà|Indica che un'impostazione appartiene a una categoria speciale, predefinita, ad esempio una stringa di connessione, che suggerisce un'elaborazione speciale dal provider di impostazioni. Le categorie predefinite per questo attributo sono definite per il <xref:System.Configuration.SpecialSetting> enumerazione.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Entrambi|Specifica un meccanismo di serializzazione preferito per un gruppo di impostazioni o proprietà. Meccanismi di serializzazione disponibili sono definiti per il <xref:System.Configuration.SettingsSerializeAs> enumerazione.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Proprietà|Specifica che un provider di impostazioni deve disabilitare tutte le funzionalità di aggiornamento dell'applicazione per la proprietà contrassegnata.|  
  
 *Classe* indica che l'attributo può essere applicato solo a una classe wrapper di impostazioni dell'applicazione. *Proprietà* indica che l'attributo può essere applicato solo alle proprietà delle impostazioni. *Entrambi* indica che l'attributo può essere applicato a entrambi i livelli.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [Procedura: creare le impostazioni applicazione](http://msdn.microsoft.com/en-us/53b3af80-1c02-4e35-99c6-787663148945)
