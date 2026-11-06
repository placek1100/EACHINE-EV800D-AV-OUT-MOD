## ⚠️ Ostrzeżenie (Disclaimer)
Modyfikację wykonujesz na własne ryzyko. Nie daję gwarancji, że układ w Twoich goglach wygląda tak samo, zwłaszcza dlatego, że są to bardzo często podrabiane gogle.

## Jak to działa?
Dzięki inżynierii wstecznej udało mi się odtworzyć część toru wideo. 

Sygnał z dwóch modułów RX5808 trafia do multipleksera ET3157, który realizuje funkcję diversity. Następnie przez kondensator 100uF trafia na bazę tranzystora NPN pełniącego rolę bufora prądowego. Stamtąd trafia na kolejny układ ET3157, który najprawdopodobniej decyduje, czy obraz podawany na ekran idzie z anten czy wejścia AV IN (piszę "najprawdopodobniej", ponieważ sam nie prześledziłem tej części układu, natomiast jest to jedyne logiczne miejsce na realizację tego przełączenia).

Sygnał analogowy należy pobrać po tranzystorze, ale jeszcze przed drugim układem ET3157. Trzeba również zlokalizować dowolną masę na płytce. 

<img width="1248" height="1664" alt="20261106_210658" src="https://github.com/user-attachments/assets/9def47fc-9716-4736-8194-5d9fc597de42" />

Można wykorzystać istniejący w goglach port AV IN i wypuścić nim nasz sygnał. Wymaga to odcięcia tego portu od aktualnych ścieżek. Ja wolałem wypuścić przewody na zewnątrz, dokładając nowy port.

Jeśli chcesz wykorzystać te gogle jako VRX dla gogli Walksnail Avatar X, to pamiętaj, że oryginalna wtyczka w goglach jest 5-pin do 4-pin. Tip wtyczki 5-pin jest NC, ale nie można zastąpić go wtyczką 4-pin, bo może to wywołać zwarcie. Tak samo po drugiej stronie - mimo, że używamy tylko 2 pinów (AV i GND), to nie możemy zastąpić wtyczki na 2-pin, bo zewrzemy pozostałe 2 piny (RX i TX). 

<img width="1261" height="432" alt="image" src="https://github.com/user-attachments/assets/2aae0d13-dc18-49db-b6c6-8951a26b7c02" />

Po podłączeniu przewodów należy zmienić źródło obrazu. Aby to zrobić, trzeba trzymać przycisk BACK przez 5 sekund. W goglach są 3 tryby (wewnętrzny VRX / CVBS / HDMI).

Na koniec podrzucam schemat do toru wideo.

<img width="1169" height="827" alt="Schematic_eachine-av-out-2_2026-11-06" src="https://github.com/user-attachments/assets/52a95ba5-cb78-443d-a119-5d9c807b266d" />
