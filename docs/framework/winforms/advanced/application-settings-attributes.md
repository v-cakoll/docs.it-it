---
title: Attributi delle impostazioni delle applicazioni
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: b38ed931cab3a333a56dd027d5843b1c8f00dcb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916673"
---
# <a name="application-settings-attributes"></a>Attributi delle impostazioni delle applicazioni
L'architettura delle impostazioni dell'applicazione fornisce molti attributi che possono essere applicati alla classe wrapper delle impostazioni delle applicazioni o alle rispettive proprietà. Questi attributi vengono esaminati in fase di esecuzione dall'infrastruttura delle impostazioni dell'applicazione, spesso in particolare dal provider di impostazioni, per adattarne il funzionamento alle esigenze indicate del wrapper personalizzato.  
  
 La tabella seguente elenca gli attributi che possono essere applicati alla classe wrapper delle impostazioni dell'applicazione, alle singole proprietà della classe o a entrambe. Per definizione, è necessario applicare un solo attributo di ambito, ovvero**UserScopedSettingAttribute** o **ApplicationScopedSettingAttribute**, a ogni proprietà delle impostazioni.  
  
> [!NOTE]
> Un provider di impostazioni personalizzato, derivato dalla <xref:System.Configuration.SettingsProvider> classe, è necessario solo per riconoscere i tre attributi seguenti: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**e **DefaultSettingValueAttribute**.  
  
|Attributo|destinazione|DESCRIZIONE|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Entrambi|Specifica il nome breve del provider di impostazioni da usare per la persistenza.<br /><br /> Se questo attributo non viene specificato, viene utilizzato il provider <xref:System.Configuration.LocalFileSettingsProvider>predefinito.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Entrambi|Definisce una proprietà come impostazione dell'applicazione con ambito di utente.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Entrambi|Definisce una proprietà come impostazione dell'applicazione con ambito di applicazione.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Proprietà|Specifica una stringa che può essere deserializzata dal provider nel valore predefinito hardcoded per questa proprietà.<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider> Non richiede questo attributo e sostituirà qualsiasi valore fornito da questo attributo se è già presente un valore persistente.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Proprietà|Fornisce il test descrittivo per una singola impostazione, utilizzata principalmente dagli strumenti Runtime e della fase di progettazione.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Classe|Fornisce un nome esplicito per un gruppo di impostazioni. Se questo attributo non è presente <xref:System.Configuration.ApplicationSettingsBase> , utilizza il nome della classe wrapper.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Classe|Fornisce il test descrittivo per un gruppo di impostazioni, usato principalmente dagli strumenti di runtime e in fase di progettazione.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Entrambi|Specifica zero o più servizi di gestibilità che devono essere forniti al gruppo di impostazioni o alla proprietà. I servizi disponibili sono descritti dall' <xref:System.Configuration.SettingsManageability> enumerazione.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Proprietà|Indica che un'impostazione appartiene a una categoria speciale e predefinita, ad esempio una stringa di connessione, che suggerisce un'elaborazione speciale da parte del provider di impostazioni. Le categorie predefinite per questo attributo sono definite dall' <xref:System.Configuration.SpecialSetting> enumerazione.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Entrambi|Specifica un meccanismo di serializzazione preferito per un gruppo di impostazioni o una proprietà. I meccanismi di serializzazione disponibili sono definiti <xref:System.Configuration.SettingsSerializeAs> dall'enumerazione.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Proprietà|Specifica che un provider di impostazioni deve disabilitare tutte le funzionalità di aggiornamento dell'applicazione per la proprietà contrassegnata.|  
  
 La *classe* indica che l'attributo può essere applicato solo a una classe wrapper delle impostazioni dell'applicazione. *Proprietà* indica che l'attributo può essere applicato solo alle proprietà delle impostazioni. *Entrambi* indica che l'attributo può essere applicato a entrambi i livelli.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Application Settings Architecture](application-settings-architecture.md)
- [Procedura: Crea impostazioni applicazione](how-to-create-application-settings.md)
