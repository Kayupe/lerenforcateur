CREATE TABLE `membres` (
  `id` int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `pseudo` varchar(25) COLLATE utf8_unicode_ci NOT NULL,
  `mdp` char(32) COLLATE utf8_unicode_ci NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;

// Partie router

define('VIEW_PATH', dirname(__DIR__).'/views');

$router->map('GET', '/presentation',function(){
    require VIEW_PATH.'/index.php';
});

$router->map('GET', '/Activites',function(){
    require VIEW_PATH.'/mission.php';
});

$match=$router->match();
$match['target']();