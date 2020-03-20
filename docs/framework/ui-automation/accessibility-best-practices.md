---
title: Procedure consigliate per l'accesso facilitato
ms.date: 03/30/2017
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
ms.openlocfilehash: c6f0f31260ffae43e59703ef53dd7ef30a73320b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180293"
---
# <a name="accessibility-best-practices"></a>Procedure consigliate per l'accesso facilitato
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 L'implementazione delle procedure consigliate seguenti nei controlli o nelle applicazioni ne migliorerà l'accessibilità per gli utenti che utilizzano dispositivi di assistive technology. Molte di queste procedure consigliate si concentrano su una buona progettazione dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] . Ogni procedura consigliata include informazioni sull'implementazione per i controlli o le applicazioni di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] . In molti casi, il lavoro per soddisfare le seguenti procedure consigliate è già incluso nei controlli di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] .  
  
<a name="Programmatic_Access"></a>
## <a name="programmatic-access"></a>Accesso a livello di codice  
 L'accesso a livello di codice consente di garantire che tutti gli elementi [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] siano etichettati, che vengano esposti i valori delle proprietà e vengano generati gli eventi appropriati. Per i controlli standard di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , gran parte del lavoro è già eseguita tramite <xref:System.Windows.Automation.Peers.AutomationPeer>. I controlli personalizzati richiedono operazioni aggiuntive per garantire che l'accesso a livello di codice sia implementato correttamente.  
  
<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>
### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a>Abilitare l'accesso a livello di codice a tutti gli elementi dell'interfaccia utente e al testo  
 Gli elementi dell'interfaccia utente devono abilitare l'accesso a livello di codice. Se [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] è un controllo standard di [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , il supporto per l'accesso a livello di codice è incluso nel controllo. Se il controllo è personalizzato, cioè un controllo che è stato sottoclassato da un controllo comune o da un controllo sottoclassato da Control, è necessario verificare l'implementazione di <xref:System.Windows.Automation.Peers.AutomationPeer> per le aree che possono richiedere modifiche.  
  
 Attenendosi a questa procedura consigliata, i fornitori di [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]tecnologie per l'amichetto possono identificare e manipolare gli elementi del prodotto.  
  
<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>
### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a>Inserire nomi, titoli e descrizioni in oggetti di interfaccia utente, frame e pagine  
 Le tecnologie per l'accessibilità, in special modo le utilità per la lettura dello schermo, usano il titolo per comprendere la posizione del frame, dell'oggetto o della pagina nello schema di navigazione. Pertanto, il titolo deve essere molto descrittivo. Ad esempio, un titolo della pagina Web "pagina Web di Microsoft" è inutile se l'utente ha esplorato a fondo un'area particolare. Un titolo descrittivo è fondamentale per gli utenti affetti da cecità, che dipendono dalle utilità per la lettura dello schermo. Analogamente, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] per <xref:System.Windows.Automation.AutomationProperties.NameProperty> <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> i controlli, e sono importanti per i dispositivi di assistive technology.  
  
 Attenendosi a questa procedura consigliata, [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] le tecnologie per l'accesso facilitato possono identificare e manipolare nei controlli e nelle applicazioni di esempio.  
  
<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>
### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a>Verificare che gli eventi a livello di codice siano attivati da tutte le attività dell'interfaccia utente  
 Attenersi a questa procedura consigliata consente alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] tecnologie assistive di ascoltare le modifiche e notificare all'utente tali modifiche.  
  
<a name="User_Settings"></a>
## <a name="user-settings"></a>Impostazioni utente  
 La procedura consigliata in questa sezione garantisce che i controlli o le applicazioni non eseguono l'override delle impostazioni utente.  
  
<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>
### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a>Rispettare tutte le impostazioni a livello di sistema e non interferire con le funzioni di accesso facilitato  
 Gli utenti possono usare il pannello di controllo per impostare un flag a livello di sistema; altri flag possono essere impostati a livello di codice. Queste impostazioni non devono essere modificate da controlli o applicazioni. Inoltre, le applicazioni devono supportare le impostazioni di accessibilità del sistema operativo host.  
  
 Seguendo questa procedura consigliata gli utenti potranno configurare le impostazioni di accessibilità e sapere che queste non verranno modificate dalle applicazioni.  
  
<a name="Visual_UI_Design"></a>
## <a name="visual-ui-design"></a>Progettazione dell'interfaccia utente visiva  
 Le procedure consigliate in questa sezione garantiscono che i controlli o le applicazioni utilizzino in modo efficace il colore e le immagini e siano in grado di essere utilizzati dalle tecnologie di Assistive Technology.  
  
<a name="Don_t_Hard_Code_Colors"></a>
### <a name="dont-hard-code-colors"></a>Non impostare i colori come hardcoded  
 È possibile che le persone daltoniche, con ipovisione o che usano uno schermo in bianco e nero non possano usare applicazioni con colori hardcoded.  
  
 Seguendo questa procedura consigliata gli utenti potranno modificare le combinazioni di colori in base alle proprie esigenze.  
  
<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>
### <a name="support-high-contrast-and-all-system-display-attributes"></a>Supportare il contrasto elevato e tutti gli attributi di visualizzazione del sistema  
 Le applicazioni non devono interrompere o disabilitare le impostazioni di contrasto, le selezioni dei colori o altre impostazioni e attributi di visualizzazione a livello di sistema selezionati dall'utente. Le impostazioni a livello di sistema adottate da un utente migliorano l'accessibilità delle applicazioni, pertanto non deve essere disabilitate o ignorate dalle applicazioni. I colori devono essere usati nella loro corretta combinazione di colore di primo piano e di sfondo per fornire un contrasto appropriato. I colori non correlati non devono essere combinati e i colori non devono essere invertiti.  
  
 Molti utenti richiedono specifiche combinazioni di contrasto elevato, ad esempio testo bianco su sfondo nero. L'inversione dei colori, usando testo nero su sfondo bianco, provoca la smarginatura del colore di sfondo sul colore di primo piano, rendendo difficile la lettura per alcuni utenti.  
  
<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>
### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a>Verificare che tutti gli elementi dell'interfaccia utente siano ridimensionati correttamente in base alle impostazioni DPI  
 Assicurarsi [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] che tutti siano in grado di scalare correttamente di qualsiasi impostazione di punti per pollice (dpi). Inoltre, assicurati [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] che gli elementi si adattino a uno schermo di 1024 x 768 con 120 punti per pollice (dpi).  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navigazione  
 Le procedure consigliate in questa sezione garantiscono che la navigazione per applicazioni e controlli sia stata gestita.  
  
<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>
### <a name="provide-keyboard-interface-for-all-ui-elements"></a>Fornire l'interfaccia della tastiera per tutti gli elementi dell'interfaccia utente  
 Le tabulazioni, specialmente quando pianificate con molta attenzione, offrono agli utenti un altro modo per esplorare l' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
 Le applicazioni devono fornire le interfacce di tastiera seguenti:  
  
- tabulazioni per tutti i controlli con cui l'utente può interagire, ad esempio pulsanti, collegamenti o caselle di riepilogo  
  
- ordine di tabulazione logico  
  
<a name="Show_the_Keyboard_Focus"></a>
### <a name="show-the-keyboard-focus"></a>Mostrare lo stato attivo della tastiera  
 Gli utenti devono sapere quale oggetto ha lo stato attivo in modo da poter prevedere l'effetto delle pressioni dei tasti. Per evidenziare lo stato attivo, usare colori, tipi di carattere o grafiche quali rettangoli o l'ingrandimento. Per evidenziare lo stato attivo a livello acustico, modificare il volume, il passo o la qualità tonale.  
  
 Per evitare confusione, le applicazioni devono nascondere tutti gli indicatori visivi dello stato attivo e disattivare le selezioni che si trovano in finestre (o riquadri) non attive.  
  
 Le applicazioni devono eseguire le operazioni seguenti con lo stato attivo:  
  
- un elemento deve avere sempre lo stato attivo  
  
- lo stato attivo deve essere visibile e ovvio  
  
- le selezioni e/o gli elementi specifici devono essere evidenziati visivamente  
  
<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>
### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a>Supportare gli standard di esplorazione e schemi di navigazione potenti  
 Diversi aspetti della navigazione da tastiera forniscono modi diversi agli utenti per spostarsi nell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
 Le applicazioni devono fornire le interfacce di tastiera seguenti:  
  
- tasti di scelta rapida e tasti di scelta sottolineati per tutti i comandi, menu e controlli  
  
- tasti di scelta rapida per collegamenti importanti  
  
- tutte le voci di menu hanno un tasto di scelta; tutti i pulsanti hanno tasti di scelta rapida, tutti i comandi hanno un tasto di scelta rapida.  
  
<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>
### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a>Non consentire alla posizione del mouse di interferire con la navigazione da tastiera  
 La posizione del mouse non dovrebbe interferire con la navigazione da tastiera. Ad esempio, se il mouse è posizionato in un punto e l'utente si sposta con la tastiera, un clic del mouse non dovrebbe verificarsi a meno che non avviato dall'utente.  
  
<a name="Multimodal_Interface"></a>
## <a name="multimodal-interface"></a>Interfaccia multimodale  
 Le procedure consigliate in questa sezione garantiscono che l'applicazione [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] includa alternative per gli elementi visivi.  
  
<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>
### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a>Fornire equivalenti selezionabili dall'utente per gli elementi non di testo  
 Per ogni elemento non di testo, fornire un equivalente selezionabile dall'utente per testo, trascrizioni o descrizioni audio, ad esempio testo alternativo, didascalie o commenti visivi.  
  
 Gli elementi non di testo includono un'ampia gamma di elementi dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] tra cui: immagini, aree della mappa immagine, animazioni, applet, frame, script, pulsanti grafici, suoni, file audio e video autonomi. Gli elementi non di testo sono importanti quando contengono informazioni visive, riconoscimento vocale o informazioni audio generali a cui l'utente deve accedere per comprendere il contenuto dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>
### <a name="use-color-but-also-provide-alternatives-to-color"></a>Usare il colore, ma fornire anche alternative al colore  
 Usare il colore per migliorare, evidenziare o avvalorare le informazioni visualizzate in altri modi, ma che non comunicano informazioni con i soli colori. Gli utenti daltonici o che usano uno schermo monocromatico necessitano di alternative ai colori.  
  
<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>
### <a name="use-standard-input-apis-with-device-independent-calls"></a>Usare le API di input standard con chiamate indipendenti dal dispositivo  
 Le chiamate indipendenti dal dispositivo garantiscono l'uguaglianza delle funzionalità [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]di tastiera e mouse, fornendo al contempo la tecnologia assistiva con le informazioni necessarie sull'oggetto .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.Peers>
- [Esempio di controllo personalizzato NumericUpDown con supporto di tema e automazione interfaccia utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))
- [Linee guida per la progettazione dell'interfaccia utente della tastiera](https://docs.microsoft.com/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
