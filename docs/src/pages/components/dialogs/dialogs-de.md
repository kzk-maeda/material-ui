---
title: React Dialog component
components: Dialog, DialogTitle, DialogContent, DialogContentText, DialogActions, Slide
githubLabel: 'component: Dialog'
materialDesign: https://material.io/components/dialogs
waiAria: 'https://www.w3.org/TR/wai-aria-practices/#dialog_modal'
---

# Dialog

<p class="description">Dialoge informieren Benutzer über eine Aufgabe und können wichtige Informationen enthalten, Entscheidungen erfordern oder mehrere Aufgaben umfassen.</p>

Ein [Dialog](https://material.io/design/components/dialogs.html) ist ein Typ von [modalen](/components/modal/) Fenstern, der vor dem App-Inhalt angezeigt wird, um wichtige Informationen bereitzustellen oder um eine Entscheidung zu bitten. Dialoge deaktivieren alle App-Funktionen, wenn sie angezeigt werden, und bleiben auf dem Bildschirm, bis sie bestätigt, abgewiesen oder eine erforderliche Aktion ausgeführt wurde.

Dialoge sind absichtlich unterbrechend und sollten sparsam eingesetzt werden.

{{"component": "modules/components/ComponentLinkHeader.js"}}

## Einfache Dialoge

Simple dialogs can provide additional details or actions about a list item. For example, they can display avatars, icons, clarifying subtext, or orthogonal actions (such as adding an account).

Berührungsmechanik:

- Durch die Auswahl einer Option wird die Option sofort übernommen und das Menü geschlossen
- Durch Berühren außerhalb des Dialogs oder Drücken von Zurück wird die Aktion abgebrochen und der Dialog geschlossen

{{"demo": "pages/components/dialogs/SimpleDialog.js"}}

## Warnungen

Alarme sind dringende Unterbrechungen, die eine Bestätigung erfordern und den Benutzer über eine Situation informieren.

Die meisten Alarme benötigen keine Titel. They summarize a decision in a sentence or two by either:

- Eine Frage stellen (zB "Dieses Gespräch löschen?")
- Eine Aussage zu den Aktionsschaltflächen machen

Use title bar alerts only for high-risk situations, such as the potential loss of connectivity. Users should be able to understand the choices based on the title and button text alone.

Falls ein Titel erforderlich ist:

- Verwenden Sie eine klare Frage oder eine Erklärung mit einer Erläuterung im Inhaltsbereich, z. B. "USB-Speicher löschen?".
- Avoid apologies, ambiguity, or questions, such as "Warning!" or "Are you sure?"

{{"demo": "pages/components/dialogs/AlertDialog.js"}}

## Übergänge

Sie können den Übergang auch austauschen. Das nächste Beispiel verwendet `Slide (Gleiten)`.

{{"demo": "pages/components/dialogs/AlertDialogSlide.js"}}

## Formulardialoge

Formulardialoge ermöglichen Benutzern das Ausfüllen von Formularfeldern innerhalb eines Dialogs. Wenn Ihre Seite beispielsweise potenziellen Abonnenten zur Eingabe ihrer E-Mail-Adresse auffordert, können sie das E-Mail-Feld ausfüllen und auf "Senden" klicken.

{{"demo": "pages/components/dialogs/FormDialog.js"}}

## Benutzerdefinierter Dialoge

Hier ist ein Beispiel zum Anpassen der Komponente. Mehr dazu erfahren Sie auf der [Überschreibungsdokumentationsseite](/customization/how-to-customize/).

Das Dialogfeld verfügt über eine Schaltfläche zum Schließen, um die Benutzerfreundlichkeit zu verbessern.

{{"demo": "pages/components/dialogs/CustomizedDialogs.js"}}

## Vollbild-Dialoge

{{"demo": "pages/components/dialogs/FullScreenDialog.js"}}

## Optionale Größen

Sie können die maximale Breite eines Dialogs festlegen, indem Sie die `maxWidth` Eigenschaft in Kombination mit dem boolean `fullWidth` verwenden. Wenn die Eigenschaft `fullWidth` wahr ist, wird der Dialog basierend auf dem Wert `maxWidth` angepasst.

{{"demo": "pages/components/dialogs/MaxWidthDialog.js"}}

## Responsive Vollbild

You may make a dialog responsively full screen using [`useMediaQuery`](/components/use-media-query/#usemediaquery).

```jsx
import useMediaQuery from '@material-ui/core/useMediaQuery';

function MyComponent() {
  const theme = useTheme();
  const fullScreen = useMediaQuery(theme.breakpoints.down('sm'));

  return <Dialog fullScreen={fullScreen} />
}
```

{{"demo": "pages/components/dialogs/ResponsiveDialog.js"}}

## Bestätigungsdialoge

Bestätigungsdialogfelder erfordern, dass Benutzer ihre Wahl explizit bestätigen, bevor eine Option festgelegt wird. For example, users can listen to multiple ringtones but only make a final selection upon touching "OK".

Touching "Cancel" in a confirmation dialog, or pressing Back, cancels the action, discards any changes, and closes the dialog.

{{"demo": "pages/components/dialogs/ConfirmationDialog.js"}}

## Ziehbarer Dialog

Sie können einen ziehbaren Dialog erstellen, indem Sie [react-draggable](https://github.com/mzabriskie/react-draggable) nutzen. Dazu können Sie die importierte `Draggable` Komponente als `PaperComponent` der `Dialog` Komponente übergeben. Dadurch wird der gesamte Dialog verschiebbar.

{{"demo": "pages/components/dialogs/DraggableDialog.js"}}

## Blättern von langen Inhalten

When dialogs become too long for the user's viewport or device, they scroll.

- `scroll=paper`: Der Inhalt des Dialogs scrollt innerhalb des Papierelements.
- `scroll=body`: Der Inhalt des Dialogs scrollt innerhalb des Body-Elements.

Probieren Sie die Demo aus, um zu sehen, was wir meinen:

{{"demo": "pages/components/dialogs/ScrollDialog.js"}}

## Performance

Folgen Sie den [Modal Zugänglichkeit Abschnitt](/components/modal/#performance).

## Einschränkungen

Follow the [Modal limitations section](/components/modal/#limitations).

## Barrierefreiheit

Folgen Sie dem [Modal Zugänglichkeit Abschnitt](/components/modal/#accessibility).
