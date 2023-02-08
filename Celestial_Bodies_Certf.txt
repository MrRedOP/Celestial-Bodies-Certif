-
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying(30) NOT NULL,
    has_life boolean NOT NULL,
    random_text text,
    distance_mi integer,
    age_ly numeric(6,1)
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying(30) NOT NULL,
    has_life boolean NOT NULL,
    random_text text,
    distance_mi integer,
    age_ly numeric(3,1),
    planet_id integer
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name character varying(30) NOT NULL,
    has_life boolean NOT NULL,
    random_text text,
    distance_mi integer,
    age_ly numeric(6,1),
    star_id integer
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(30) NOT NULL,
    has_life boolean NOT NULL,
    random_text text,
    distance_mi integer,
    age_ly numeric(6,1),
    galaxy_id integer
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: wormholes; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.wormholes (
    wormholes_id integer NOT NULL,
    name character varying(30) NOT NULL,
    has_life boolean NOT NULL,
    random_text text,
    distance_mi integer,
    age_ly numeric(6,1),
    galaxy_id integer
);


ALTER TABLE public.wormholes OWNER TO freecodecamp;

--
-- Name: wormholes_wormholes_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.wormholes_wormholes_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.wormholes_wormholes_id_seq OWNER TO freecodecamp;

--
-- Name: wormholes_wormholes_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.wormholes_wormholes_id_seq OWNED BY public.wormholes.wormholes_id;


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Name: wormholes wormholes_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.wormholes ALTER COLUMN wormholes_id SET DEFAULT nextval('public.wormholes_wormholes_id_seq'::regclass);


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (1, 'expeliermus c', true, 'no hablamos de expeliermus a', 63, 126.0);
INSERT INTO public.galaxy VALUES (2, 'expeliermus b', true, 'excusa1', 0, 10.0);
INSERT INTO public.galaxy VALUES (3, 'galactitus', true, 'hiah', 57, 89.0);
INSERT INTO public.galaxy VALUES (4, 'hiah hiahc', true, 'im a supernova', 63, 126.0);
INSERT INTO public.galaxy VALUES (5, 'estrellusenfermus', true, 'defensis', 0, 10.0);
INSERT INTO public.galaxy VALUES (6, 'expeliermus a', false, 'rip', 0, 9.0);


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (1, 'luna 1', true, 'asfdagds', 563, 69.0, NULL);
INSERT INTO public.moon VALUES (2, 'luna 2', true, 'asfahfsjhasdagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (3, 'luna 3', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (4, 'luna 4', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (5, 'luna 5', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (6, 'luna 6', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (7, 'luna 7', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (8, 'luna 8', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (9, 'luna 9', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (10, 'luna 10', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (11, 'luna 11', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (12, 'luna 12', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (13, 'luna 13', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (14, 'luna 16', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (15, 'luna 15', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (16, 'luna 14', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (17, 'luna 19', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (18, 'luna 18', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (19, 'luna 17', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (20, 'luna 22', true, 'asfahfsjhasdhyagds', 563, 96.0, NULL);
INSERT INTO public.moon VALUES (21, 'luna 21', false, 'tamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (22, 'luna 20', false, 'tamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (23, 'estresha 1', true, 'billa billa estellita', 63, 16.5, NULL);
INSERT INTO public.moon VALUES (24, 'estresha 2', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (25, 'estresha 3', false, 'notamuertatambien', 857, 89.0, NULL);
INSERT INTO public.moon VALUES (26, 'estresha 6', true, 'billa billa estellita', 63, 16.5, NULL);
INSERT INTO public.moon VALUES (27, 'estresha 5', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.moon VALUES (28, 'estresha 4', false, 'notamuertatambien', 857, 89.0, NULL);


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (1, 'El brishante', true, 'billa billa estellita', 63, 126.0, NULL);
INSERT INTO public.planet VALUES (2, 'Uranus', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.planet VALUES (3, 'Tierra en 2930', false, 'notamuertatambien', 857, 89.0, NULL);
INSERT INTO public.planet VALUES (4, 'nombregenerico2', true, 'billa billa estellita', 63, 126.0, NULL);
INSERT INTO public.planet VALUES (5, 'Ricaenagua', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.planet VALUES (6, 'Nostrasladamus', false, 'notamssusustambien', 857, 89.0, NULL);
INSERT INTO public.planet VALUES (7, 'nombregenerico1', true, 'asdf', 63, 126.0, NULL);
INSERT INTO public.planet VALUES (8, 'Ricarena', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.planet VALUES (9, 'BadBunnyLand', false, 'snotamssusustambien', 857, 89.0, NULL);
INSERT INTO public.planet VALUES (10, 'nombregenerico5', true, 'aasdagfsdf', 63, 126.0, NULL);
INSERT INTO public.planet VALUES (11, 'Tamuerta', true, 'anotamuerta', 0, 10.0, NULL);
INSERT INTO public.planet VALUES (12, 'Sahara', false, 'tadesierto', 857, 89.0, NULL);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (1, 'estresha a', true, 'billa billa estellita', 63, 126.0, NULL);
INSERT INTO public.star VALUES (2, 'estresha b', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.star VALUES (3, 'estresha c', false, 'notamuertatambien', 857, 89.0, NULL);
INSERT INTO public.star VALUES (4, 'estresha f', true, 'billa billa estellita', 63, 126.0, NULL);
INSERT INTO public.star VALUES (5, 'estresha e', true, 'notamuerta', 0, 10.0, NULL);
INSERT INTO public.star VALUES (6, 'estresha d', false, 'notamuertatambien', 857, 89.0, NULL);


--
-- Data for Name: wormholes; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.wormholes VALUES (1, 'Dr.Stone', true, 'El piedras', NULL, NULL, NULL);
INSERT INTO public.wormholes VALUES (2, 'EM1', true, 'elmalote1', NULL, NULL, NULL);
INSERT INTO public.wormholes VALUES (3, 'XR3', false, 'siteveoteparto', NULL, NULL, NULL);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 6, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 28, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 12, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 6, true);


--
-- Name: wormholes_wormholes_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.wormholes_wormholes_id_seq', 3, true);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: galaxy unique_galaxy; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT unique_galaxy UNIQUE (name);


--
-- Name: moon unique_moon; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT unique_moon UNIQUE (name);


--
-- Name: planet unique_planet; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT unique_planet UNIQUE (name);


--
-- Name: star unique_star; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT unique_star UNIQUE (name);


--
-- Name: wormholes unique_wormholes; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.wormholes
    ADD CONSTRAINT unique_wormholes UNIQUE (name);


--
-- Name: wormholes wormholes_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.wormholes
    ADD CONSTRAINT wormholes_pkey PRIMARY KEY (wormholes_id);


--
-- Name: moon moon_planet_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_planet_id_fkey FOREIGN KEY (planet_id) REFERENCES public.planet(planet_id);


--
-- Name: planet planet_star_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_star_id_fkey FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: star star_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- Name: wormholes wormholes_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.wormholes
    ADD CONSTRAINT wormholes_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--