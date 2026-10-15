# Sem5_JiPP
  # Projekt gry na micro:bit  
Głównym elementem projektu jest zręcznościowa gra działająca na mikrokontrolerze BBC micro:bit. Rozgrywka polega na ciągłym unikaniu nadciągających przeszkód, a użytkownicy rywalizują o przetrwanie jak najdłuższego czasu na wzór klasycznych automatów. Gdy gracz zakończy swój bieg, wybiera na urządzeniu swój unikalny, trzyliterowy identyfikator za pomocą przycisków A i B.

  # Łączność i przesyłanie wyników
Z uwagi na brak modułu Wi-Fi w płytce micro:bit, transfer danych do komputera odbywa się za pomocą przewodu USB. Informacja o zdobytym wyniku oraz nicku wędruje przez port szeregowy wprost do otwartej karty w przeglądarce Chrome lub Edge. Obsługa standardu Web Serial API pozwala na bezpośredni, dwukierunkowy przesył tych parametrów przez stronę internetową, bez konieczności instalowania jakichkolwiek dodatkowych programów czy sterowników.

  # Technologia
Logika samej gry jest programowana przy użyciu platformy MakeCode. Aplikacja webowa została oparta na frameworku Next.js (React). Gromadzenie statystyk i wyników graczy zapewnia chmurowa baza danych PostgreSQL (Supabase), z którą strona komunikuje się bezpośrednio przez gotowe API, a całość jest hostowana na platformie Vercel.

  # Wizualizacja tablicy liderów
Wszystkie rezultaty zapisane w bazie zasilają główną, globalną tablicę wyników dostępną na żywo na stronie internetowej. Oprócz tego mikrokontroler posiada funkcję lokalnego informowania o najlepszych – po każdej zakończonej partii strona odsyła przez USB aktualny ranking, a na wbudowanej matrycy LED przewijają się pseudonimy trzech topowych graczy.
