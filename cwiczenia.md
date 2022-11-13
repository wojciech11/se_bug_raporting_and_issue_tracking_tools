# Ćwiczenia

## Dobrze mieć edytor pod ręką

```bash
sudo snap install atom --classic
```

## Przygotowanie - instalacja Dockera

```bash
# następne komendy musimy uruchomić jako root
sudo su

apt-get update ;
apt-get install -qq apt-transport-https ca-certificates curl software-properties-common ;
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - ;
add-apt-repository 'deb [arch=amd64] https://download.docker.com/linux/ubuntu '$(lsb_release -cs)' stable' ;
apt-get update ;
apt-get install -qq docker-ce ;

# 
exit
```

## Przygotowanie - uruchomienie YouTrack

Wszystkie dostępne wersje youtrack znajdziesz na [hub.docker.com/r/jetbrains](https://hub.docker.com/r/jetbrains/youtrack/tags), sprawdź przed uruchomieniem poniższej komendy czy nie ma nowszej wersji (tagu):

```bash
# z sudo
docker run  -p 8080:8080 --name wsb-youtrack jetbrains/youtrack:2022.2.60480
```

## Youtrack

1. Otwórz w przeglądarce http://127.0.0.1:8080. Token znajdziesz w ostatniej linii logów dockera.
2. Ustaw hasło takie, żeby nie zapomnieć, np., `admin`.
3. Wybierz Explore the demo project.

## Przydatne komenty

Zauważ, na linuxie musisz poprzedzić komendy `sudo`:

```bash
# w nowym terminany możesz wyświetlić
# działające dockery
docker ps

# pokaż wszystkie włączając te zatrzymane
docker ps -a

# jeśli zatrzymaliśmy dockera, to możemy go
# uruchomić ponownie
docker start wsb-youtrack

# wyświetl logi
docker logs wsb-youtrack

# aby zatrzymać dockera:
docker stop wsb-youtrack
```

# Materiały dodatkowe

- [Firefox bug reports](https://support.mozilla.org/en-US/kb/file-bug-report-or-feature-request-mozilla)
- [Tworzenie Szablonu dla Github Issue](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)
- [Szablony Firefox mobile github](https://github.com/mozilla-mobile/fenix/issues/new/choose)
- [Youtrack @ hub.docker.com](https://hub.docker.com/r/jetbrains/youtrack/)
- [Bitnami stack containers](https://bitnami.com/stacks/containers)
- [How to file a good browser bug](https://web.dev/how-to-file-a-good-bug/)
