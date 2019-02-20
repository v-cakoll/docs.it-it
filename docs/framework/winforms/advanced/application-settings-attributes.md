---
title: Attributi delle impostazioni delle applicazioni
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: a46f1fd14400995fef91c117502df24eae613fac
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442555"
---
# <a name="application-settings-attributes"></a>Attributi delle impostazioni delle applicazioni
L'architettura di impostazioni dell'applicazione fornisce numerosi attributi che possono essere applicati per la classe wrapper di impostazioni o alle singole proprietà. Questi attributi vengono esaminati in fase di esecuzione per l'infrastruttura di impostazioni dell'applicazione, spesso in modo specifico il provider di impostazioni, per adattare il suo funzionamento alle esigenze del wrapper personalizzate dichiarate.  
  
 Nella tabella seguente elenca gli attributi che possono essere applicati per la classe wrapper delle impostazioni dell'applicazione, le singole proprietà di questa classe o entrambi. Per definizione, un attributo singolo ambito, ovvero**UserScopedSettingAttribute** oppure **ApplicationScopedSettingAttribute**, deve essere applicato a tutte le proprietà delle impostazioni.  
  
> [!NOTE]
>  Un provider di impostazioni personalizzato, derivato dal <xref:System.Configuration.SettingsProvider> classe, è richiesto solo per riconoscere i tre attributi seguenti: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, e **DefaultSettingValueAttribute**.  
  
|Attributo|destinazione|Descrizione|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|Entrambi|Specifica il nome breve del provider di impostazioni da utilizzare per la persistenza.<br /><br /> Se questo attributo viene omesso, il provider predefinito, <xref:System.Configuration.LocalFileSettingsProvider>, verrà utilizzato.|  
|<xref:System.Configuration.UserScopedSettingAttribute>|Entrambi|Definisce una proprietà come un'impostazione con ambito di utente dell'applicazione.|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|Entrambi|Definisce una proprietà come un'impostazione con ambito di applicazione dell'applicazione.|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|Proprietà|Specifica una stringa che può essere deserializzata dal provider nel valore predefinito hardcoded per questa proprietà.<br /><br /> Il <xref:System.Configuration.LocalFileSettingsProvider> non richiede questo attributo e ignorerà qualsiasi valore fornito da questo attributo se non esiste già un valore persistente.|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|Proprietà|Fornisce il testo descrittivo per una singola impostazione, usata principalmente dagli strumenti di runtime e fase di progettazione.|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|Classe|Fornisce un nome esplicito per un gruppo di impostazioni. Se questo attributo è manca, <xref:System.Configuration.ApplicationSettingsBase> Usa il nome della classe wrapper.|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|Classe|Fornisce il testo descrittivo per un gruppo di impostazioni utilizzato principalmente dagli strumenti di runtime e fase di progettazione.|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|Entrambi|Specifica zero o più servizi la facilità di gestione che devono essere forniti per il gruppo di impostazioni o proprietà. I servizi disponibili sono descritti dal <xref:System.Configuration.SettingsManageability> enumerazione.|  
|<xref:System.Configuration.SpecialSettingAttribute>|Proprietà|Indica che un'impostazione appartiene a una categoria predefinita, speciale, ad esempio una stringa di connessione, che suggerisce un'elaborazione speciale per il provider di impostazioni. Le categorie predefinite per questo attributo sono definite dal <xref:System.Configuration.SpecialSetting> enumerazione.|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|Entrambi|Specifica un meccanismo di serializzazione preferito per un gruppo di impostazioni o proprietà. I meccanismi di serializzazione sono definiti dal <xref:System.Configuration.SettingsSerializeAs> enumerazione.|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|Proprietà|Specifica che un provider di impostazioni deve disabilitare tutte le funzionalità di aggiornamento dell'applicazione per la proprietà contrassegnata.|  
  
 *Classe* indica che l'attributo può essere applicato solo a una classe wrapper di impostazioni dell'applicazione. *Proprietà* indica che l'attributo può essere applicato solo alle proprietà delle impostazioni. *Entrambi* indica che l'attributo può essere applicato a qualsiasi livello.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.SettingsProvider>
- [Application Settings Architecture](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
- [Procedura: Creare le impostazioni dell'applicazione](how-to-create-application-settings.md)
